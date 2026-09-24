# TTA Military Optimizer (歷史巨輪 軍力最佳化計算機) ⚔️
*(Scroll down for English version)*

這是一個專為知名桌遊《歷史巨輪 (Through the Ages)》設計的輔助工具。在遊戲中，為了湊出最強的陣型，往往需要精算手中的**軍事行動點 (MA)**、**礦物** 以及 **閒置人口** 來決定哪些部隊該建造、哪些該升級。

這個網頁工具採用 **Backtracking DFS 演算法**，能在毫秒內算出在給定資源下的「最大潛在武力」，並直接列出最省資源的「最佳行動順序」。完全支援擴充版的**戰鬥機 (Air Forces)** 功能、以及**降級陣型武力 (Age - 1)** 觸發全額加成的進階規則。

本工具無伺服器後端，純前端運作，您可以直接使用手機或 iPad 的瀏覽器開啟，並加入主畫面當作 Web App 使用。支援繁體中文 (TW) 與英文 (EN)。

## 💡 新版亮點與功能

*   **最終盤面兵力視覺化:** 運算結果會自動印出完整的「最終兵種數量表格」，並標示出所有加減變化 `(+1)` `(-1)`，讓行動軌跡與結果完美對接。
*   **戰機翻倍來源拆分:** 演算法會嚴格把關「1 陣型最多配 1 戰機」的規則。結果列的武力明細會明確拆分為 `(部隊武力 + 陣型加成 + 戰機翻倍 + 額外武力)`，讓您清楚看到第二台戰鬥機是單純提供 5 點基礎部隊武力，絕無重複翻倍。
*   **無縫計入額外武力:** 您只需要直接填入科技、領袖、殖民地等帶來的「現有額外武力」，系統會自動加總至最終結果中。
*   **一鍵重置 (Reset):** 新增重置按鈕，一鍵將所有資源、兵種、額外武力歸零（閒置人口會貼心地維持在無限值的 99），方便快速測試不同路線。
*   **智慧自動解鎖:** 所有兵種的科技方塊預設為未解鎖。但當您將某個兵種的數量調整為 `> 0` 時，系統會**自動幫您勾選解鎖**，讓輸入流程如絲綢般滑順。

### 📝 實戰範例 (TW)

> 你現在在 Age II (二時代)，你除了部隊外，科技與殖民地等為你帶來了 `8` 點額外武力。你想打出手上的**「拿破崙 (1步 1騎 1砲)」**陣型。
> 你的資源有：**5 MA、12 礦物、人口無限**。
> 你場上目前只有：**2 個步兵 A** 和 **1 個騎兵 I**。
> 你想知道怎麼做才能極大化這回合的武力？

*   **操作方式：**
    *   資源輸入：5 MA, 12 礦
    *   兵種區：現有額外武力填入 `8`，步兵 A = `2`，騎兵 I = `1` (系統會自動幫您勾選騎兵I的解鎖)。
    *   目標陣型選擇：點選 `拿破崙` 圖片，來源選擇 `手中打出 (1 MA)`
*   **結果：** 點擊計算，系統會瞬間告訴你潛在的最大武力，並給出詳細的武力來源，以及最終盤面到底長什麼樣子。

---

# TTA Military Optimizer ⚔️ (English)

As enthusiasts of this wonderful game, my friends and I created a tool to calculate the maximum potential military strength and the optimal action sequence. In *Through the Ages*, finding the best combination of building and upgrading units to match a tactic—constrained by **Military Actions (MA)**, **Minerals**, and **Idle Population**—can be a brain-burner.

This tool uses a highly optimized **Backtracking DFS algorithm** to instantly solve for the maximum possible strength and outputs the exact sequence of actions with MA costs to achieve it. It features visual tactic selection, **Air Forces (Age III)** double-bonus logic, and fully supports the modern rule where units `Age - 1` still grant the full tactical bonus.

It is fully responsive and strictly client-side, allowing you to run it in any web browser or save it to your device's home screen as a standalone web app. It supports both Traditional Chinese (TW) and English (EN).

## 💡 Key Features

*   **Final Unit Grid Visualization:** The results now print a precise grid of your final army composition, highlighting additions `(+1)` and subtractions `(-1)` so you can easily verify the calculated path.
*   **Air Double Breakdown:** The algorithm strictly adheres to the "1 Air Force per 1 Formed Army" rule. The strength breakdown is now separated into `(Units + Tactic + Air Double + Extra)`, proving that surplus Air Forces only provide their base 5 strength without illegally doubling a tactic twice.
*   **Extra Strength Integration:** Simply input any passive strength you have (from techs, colonies, etc.), and it will flawlessly add to your final maximum projection.
*   **One-Click Reset:** Easily wipe the board clean to test a new scenario. It resets all values while conveniently keeping your Idle Pop at 99.
*   **Smart Auto-Unlock:** All unit technologies start locked by default. However, the moment you increase a unit's quantity above 0, the system automatically unlocks that technology for you.

### 📝 Examples (EN)

> You are in Age II and have `8` passive Extra Strength from colonies and technologies. You want to play the **"Napoleonic (1 Inf, 1 Cav, 1 Art)"** tactic from your hand.
> You have: **5 MAs, 12 Minerals, and unlimited Pop**.
> Your current army consists of: **2 Inf A** and **1 Cav I**.
> What is the absolute best way to spend your resources this turn?

*   **How to input:**
    *   Resources: 5 MA, 12 Mins
    *   Units: Current Extra Strength `8`, Inf A = `2`, Cav I = `1` (The system auto-unlocks Cav I for you).
    *   Target Tactic: Click the `Napoleonic` image, Source: `From Hand (1 MA)`
*   **Result:** Click calculate, and the algorithm will instantly give you your max potential strength, break down the exact sources, show your final army grid, and give you the step-by-step optimal sequence.