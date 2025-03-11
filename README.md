## 論文PDF:
[Hybrid Beamforming and Phase Shift Optimization with On-Off Control of RF Chain and Reflecting Element for Energy-Efficiency RIS-Aided Downlink Communications.pdf](https://github.com/user-attachments/files/19175201/Hybrid.Beamforming.and.Phase.Shift.Optimization.with.On-Off.Control.of.RF.Chain.and.Reflecting.Element.for.Energy-Efficiency.RIS-Aided.Downlink.Communications.pdf)

## Abstract
重構智能表面（Reconfigurable Intelligent Surface, RIS）因其作為6G移動網絡低成本和低功耗新興技術的潛力，最近受到了極大的關注。本文中，針對射頻鏈和反射元件在能效RIS輔助下行通訊中的開關控制，開發了一種混合波束成型和相位移優化方案，稱為BPOF方案。該混合波束成型和相位移優化方案不僅考慮了被動RIS，還考慮了主動RIS，其中被動RIS受到乘法衰減效應的影響，而主動RIS系統中的每個元件都以放大因子放大反射訊號。為了最大化傳輸速率與能耗的比值，即通常稱為能效（Energy Efficiency, EE），基於被動和主動RIS系統建立了一個最大化優化問題。此優化問題包括射頻鏈開關、RIS元件開關、波束成型和相位移問題。為了數學上解決這些多個耦合的優化變量，採用了Dinkelbach和二次變換，並使用交替優化（AO）來近似最優解。實驗結果表明，所提出的BPOF方案相比現有結果能有效提高。

## Contribution
- 如下圖所示，考慮了RIS輔助的基地台和多用戶通訊的毫米波下行鏈路網路系統。為了最大化系統的能源效率，也就是找到傳輸速率與能源消耗的平衡點，將優化基地台的波束成型與RIS上的相位位移。在波束成型的部分，將其設計為混合波束成型系統。在RIS的部分，將設計被動RIS系統與主動RIS系統並將其進行比較。為了更詳盡的探討射頻鏈與RIS元件對於能源效率的影響，將優化進行開關控制優化。

- 由於上述所提之能源效率問題為一個非凸的問題，因此將透過非凸轉凸的方法將最大化問題與限制問題作轉換。由於傳輸速率為一分數形式且擁有二次方等條件，將先透過二次轉換法將傳輸速率的部分作轉換。為了滿足問題形式的限制，也將利用半正定鬆弛等方法將其作轉換，在開關的部分也將其作限制放鬆。能源效率也為一分數問題，因此，將透過Dinkelbach轉換法將問題形式作轉換以避免分數問題。最後再利用貪婪演算法決定最優的射頻鏈開關與RIS元件開關。

- 最後在實驗結果表明，主動的RIS系統比被動的RIS系統能夠創造更好的能源效率。除了優化基地台波束成型與RIS的相位位移之外，所提出的射頻鏈開關與RIS元件開關控制優化也比全開的情況下擁有更好的效果。

![image](https://github.com/user-attachments/assets/f3c7c8ec-4fd2-45cc-8877-1830a13367a1)

## Preliminaries
- Hybrid beamforming model

此圖為基地台透過混合波束成型服務多個用戶，波束成型會影響傳輸速率與能耗，因此將優化波束成型來找到最優的傳輸速率與能耗的最佳平衡點。除了優化波束成型，可以看到圖中有RF chain開關，由於RF chain開啟時（綠色）會消耗固定能耗，所以在此也將同時考慮將哪些射頻鏈關閉（灰色）來達到最優的能源效率。

![image](https://github.com/user-attachments/assets/62d8d385-d3f3-41ba-acf1-1972d7b84dd1)

<br>
<br>

- Signal transmission model for passive and active RIS

此圖為在基地台服務多個用戶時，會透過被動RIS或主動RIS輔助來提升能源效率，因此將優化RIS上的相位位移來提升傳輸速率。除了優化相位位移外，這裡也將考慮開啟（綠色）或關閉（灰色）RIS元件來提升能源效率。

![image](https://github.com/user-attachments/assets/db35aed2-0e95-478c-b3e8-76f06ed2b809)

<br>
<br>

- Problem formulation for passive RIS system

![image](https://github.com/user-attachments/assets/823867d7-cfff-468e-a439-5bafa3bee28d)

<br>
<br>

- Problem formulation for active RIS system

![image](https://github.com/user-attachments/assets/ebef1af4-1029-4a16-b7ee-ca3d14687954)

## Scheme
在本文所提出的BPOF方案中，將使用交換優化的方式逼近最優的能源效率系統。主要會先優化基地台的部分，也就是波束成型。優化完後，再來優化RIS的部分，也就是相位位移，之後兩者不斷迭代優化直至收斂。對於波束成型將會先固定類比波束成型與射頻鏈開關的變數並透過零強迫（Zeor Forcing, ZF）優化數位波束成型，之後再經過數學式子的轉換同時優化類比波束成型以及射頻鏈開關係數。對於RIS部分，也會經過數學式子的轉換並同時優化放大器、相位位移以及RIS元件開關係數。基地台部分的參數以及RIS部分的參數不斷地透過迭代直到收歛，以下分別為BPOF方法的總圖以及優化的流程圖。

![image](https://github.com/user-attachments/assets/a43a6c0f-6093-4694-b0e2-5638762d673a)

![image](https://github.com/user-attachments/assets/687c6c03-9890-4942-b197-239f13a817e6)

<br>
<br>

經過數學轉換式之後，再經過流程圖中的phase 1與phase 2的不斷迭帶優化直到收斂後，會進入到流程圖中的phase 3，透過貪婪演算法找到最優的波束成型、相位位移以及射頻鏈、RIS元件開關的解，如下圖所示。

![image](https://github.com/user-attachments/assets/4398647d-ab8b-4ec9-9a0f-43ee5ffcecdb)

## Experimental Results

基地台將被設定在位置為(0, 0)公尺的位置上，RIS的位置將被設定在位置為(50, 10)公尺的位置上，兩個用戶端將被隨機的設定在以位置(50, 0)公尺為中心，半徑為3公尺的圓上。每個基地台配置8根天線與6個射頻鏈，每個RIS的元件數為6個，每個用戶端為配置單天線。
實驗的比較除了本文所提出之BPOF方案與Xie等人所提出之方案外，fully active與fully passive RIS分別代表主動的RIS上的元件全部為開啟以及被動的RIS上的元件全部為開啟的情況。

![image](https://github.com/user-attachments/assets/e71693d2-a864-45b9-bf65-1eb251380472)


