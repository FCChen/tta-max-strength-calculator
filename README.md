# TTA Military Optimizer (歷史巨輪 軍力最佳化計算機) ⚔️
*(Scroll down for English version)*

這是一個專為知名桌遊《歷史巨輪 (Through the Ages)》設計的輔助工具。在遊戲中，為了湊出最強的陣型，往往需要精算手中的**軍事行動點 (MA)**、**資源 (Resources)** 以及 **閒置人口** 來決定哪些部隊該建造、哪些該升級。

這個網頁工具採用 **Backtracking DFS 演算法**，能在毫秒內算出在給定資源下，針對「已在場上 (0 MA)」、「手中打出 (1 MA)」、「複製公共 (2 MA)」三種情境的**前三大最高武力陣型**。並附上可折疊的最省資源「最佳行動順序」。完全支援擴充版的**戰鬥機 (Air Forces)** 功能、以及**降級陣型武力 (Age - 1)** 觸發全額加成的進階規則。

本工具無伺服器後端，純前端運作，您可以直接使用手機或 iPad 的瀏覽器開啟，並加入主畫面當作 Web App 使用。支援繁體中文 (TW) 與英文 (EN)。

## 💡 新版亮點與功能

*   **全自動最佳化推薦:** 不必再自己盲猜哪個陣型好！系統會一次性掃描所有陣型，直接依據「耗費 0 MA / 1 MA / 2 MA」三種情境，將能獲得最高武力的前三名陣型一字排開推薦給您。
*   **清爽的折疊介面 (Accordion):** 結果頁面一開始只會顯示最乾淨的「最大武力與推薦陣型」，點擊後才會展開詳細的武力來源分析、最終盤面與動作序列。
*   **戰機與領袖的加成防呆:** 演算法嚴格把關「1 陣型最多配 1 戰機」的規則。更實裝了**長城**、**拿破侖**、**瑪琳**以及**曼哈頓計畫**這四項後期對戰局影響劇烈的特殊效果供您隨時開關，系統會完美將這些效果整合進每一條分支的結算中。
*   **智慧自動解鎖:** 所有兵種的科技方塊預設為未解鎖。但當您將某個兵種的數量調整為 `> 0` 時，系統會自動幫您勾選解鎖。

## 🛠️️ 使用說明與實戰範例

**情境：**
> 你現在在 Age II (二時代)，你除了部隊外，科技與殖民地等為你帶來了 `8` 點額外武力。
> 你的資源有：**5 MA、12 資源、人口無限**。
> 你場上目前只有：**2 個步兵 A** 和 **1 個騎兵 I**。
> 你的領袖剛好是**瑪琳**，你想知道這回合怎麼做，才能獲得全場最高武力？

*   **操作方式：**
    1.  **可用資源：** 輸入 `5 MA`，`12 資源`，人口維持預設 `99` (無限制)。
    2.  **特殊狀況：** 點選勾起 `瑪琳 (Marlene)`。
    3.  **現有兵種與額外武力：** 現有額外武力填入 `8`。調整 `步兵 A` = `2`，`騎兵 I` = `1` (系統會自動幫您將騎兵 I 亮起解鎖)。
    4.  **點擊計算：** 直接點擊「計算最大武力推薦」按鈕！
*   **結果：** 系統會瞬間為您分門別類給出推薦，演算法會自動判斷瑪琳雙倍哪一種兵種最划算，並呈現：
    *   `已在場上陣型 (耗費 0 MA)` 的前三大最高武力選擇。
    *   `手中打出陣型 (耗費 1 MA)` 的前三大最高武力選擇 (例如推薦你打出某個陣型)。
    *   `複製公共陣型 (耗費 2 MA)` 的前三大最高武力選擇。
    展開您有興趣（或剛好手上有）的陣型，就能看見對應的最優解動作順序！

---

# TTA Military Optimizer ⚔️ (English)

As enthusiasts of this wonderful game, my friends and I created a tool to calculate the maximum potential military strength and the optimal action sequence. In *Through the Ages*, finding the best combination of building and upgrading units to match a tactic—constrained by **Military Actions (MA)**, **Resources**, and **Idle Population**—can be a brain-burner.

This tool uses a highly optimized **Backtracking DFS algorithm** to instantly scan all tactics and output the **Top 3 combinations** for three scenarios: Active (0 MA), From Hand (1 MA), and Copy Common (2 MA). It features an elegant accordion interface, **Air Forces (Age III)** double-bonus logic, and fully supports the modern rule where units `Age - 1` still grant the full tactical bonus.

It is fully responsive and strictly client-side, allowing you to run it in any web browser or save it to your device's home screen as a standalone web app. It supports both Traditional Chinese (TW) and English (EN).

## 💡 Key Features

*   **Auto-Recommendation Engine:** Stop guessing which tactic is best! Simply input your resources and current units. The algorithm evaluates all possibilities and recommends the Top 3 highest-yielding tactics based on your available MA budgets (0, 1, or 2 MA cost).
*   **Edge Case Handlers:** Built-in dynamic toggles for game-changing effects like **Great Wall**, **Napoleon**, **Marlene**, and the **Manhattan Project**. The algorithm effortlessly incorporates these into its optimization branches.
*   **Clean Accordion UI:** The results initially display only the crucial info: "Tactic Name & Max Strength". Click any recommendation to expand its detailed breakdown, final unit grid, and action sequence.
*   **Air Double Breakdown:** The algorithm strictly adheres to the "1 Air Force per 1 Formed Army" rule. The strength breakdown is separated into `(Units + Tactic + Air Double + Manhattan + Extra)`, proving exactly where your points are coming from.
*   **Smart Auto-Unlock:** All unit technologies start locked by default. However, the moment you increase a unit's quantity above 0, the system automatically unlocks that technology for you.

## 🛠️ How to Use & Example

**Scenario:**
> You are in Age II and have `8` passive Extra Strength from colonies and technologies. You are currently playing as the leader **Marlene**.
> You have: **5 MAs, 12 Resources, and unlimited Pop**.
> Your current army consists of: **2 Inf A** and **1 Cav I**.
> What is the absolute best way to spend your resources this turn?

*   **How to input:**
    1.  **Available Resources:** Input `5 MA`, `12 Resources`, keep Pop at `99` (unlimited).
    2.  **Edge Cases:** Check the toggle for `Marlene`.
    3.  **Current Units:** Input Extra Strength `8`. Increase Inf A to `2`, Cav I to `1` (The system auto-unlocks Cav I for you).
    4.  **Calculate:** Click the "Calculate Best Combinations" button!
*   **Result:** The algorithm will instantly figure out which unit type Marlene should optimally double and display the Top 3 highest-strength tactics you should aim for if they were Active (0 MA), in Hand (1 MA), or Common (2 MA). Click on any recommended tactic to expand and see the exact step-by-step action sequence.