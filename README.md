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

考慮一個具有基地台（BS）和多個用戶設備（UE）的毫米波下行通信網絡系統，並輔以重構智能表面（RIS）。設N_t為基地台的發射天線個數，N_RF為射頻鏈個數，N_RIS為RIS元件個數，N_UE為用戶設備個數。因此，整個下行系統由一個配備N_t個天線和N_RF個射頻鏈的基地台提供服務給N_UE個配備單天線的用戶設備，並由配備N_RIS個元件的RIS輔助。

N<sup>t</sup>
