# TTA Military Optimizer (歷史巨輪 軍力最佳化計算機) ⚔️
*(Scroll down for English version)*

這是一個專為知名桌遊《歷史巨輪 (Through the Ages)》設計的輔助工具。在遊戲中，為了湊出最強的陣型，往往需要精算手中的**軍事行動點 (MA)**、**礦物** 以及 **閒置人口** 來決定哪些部隊該建造、哪些該升級。

這個網頁工具採用 **Backtracking DFS 演算法**，能在毫秒內算出在給定資源下的「最大潛在武力」，並直接列出最省資源的「最佳行動順序」。所有陣型列表皆已視覺化呈現，並支援過期陣型（Antiquated Tactics）的武力衰減計算。此外，UI 已針對觸控平板優化，能透過點擊增減數值。

本工具無伺服器後端，純前端運作，您可以直接使用手機或 iPad 的瀏覽器開啟，並加入主畫面當作 Web App 使用。支援繁體中文 (TW) 與英文 (EN)。

## 💡 使用說明與變數定義

*   **可用資源:** 
    *   **軍事行動點 (MA):** 你這回合可以用的紅點數量。
    *   **礦物 (Minerals):** 你現有的礦物數量。
    *   **閒置人口 (Pop):** 你擁有的黃色工人數量（建造新部隊必備，升級部隊則不需要）。預設為 99 代表人口充足無限制。
*   **目標陣型 & 來源:** 點擊圖片選擇你想湊成的陣型（圖片需放置於 `tactic/` 資料夾內）。如果該陣型已經在你場上，選擇「已在場上 (0 MA)」。如果要從手上打出，會自動扣除 1 MA；複製別人的會自動扣除 2 MA。
*   **現有兵種數量:** 填入你場上各時代兵種的數量。表格排列已優化為「砲兵-騎兵-步兵」且由新到舊 (III -> II -> I -> A)，貼合實際玩家視角。預設值全為 0。

### 📝 實戰範例 (TW)

> 你現在在 Age II (二時代)，你想打出手上的**「拿破崙 (1步 1騎 1砲)」**陣型。
> 你的資源有：**5 MA、12 礦物、2 個閒置人口**。
> 你場上目前只有：**2 個步兵 A** 和 **1 個騎兵 I**。
> 你想知道怎麼做才能極大化這回合的武力？

*   **操作方式：**
    *   資源輸入：5 MA, 12 礦, 2 人口
    *   陣型選擇：點選 `拿破崙` 圖片，來源選擇 `從手中打出 (1 MA)`
    *   部隊輸入：步兵 A (Row A, 右欄) = `2`，騎兵 I (Row I, 中欄) = `1`
*   **結果：** 點擊計算，系統會瞬間告訴你潛在的最大武力，並給出詳細的武力來源 `(基礎 6 + 陣型加成 7)`，以及你應該：
    1. 打出手中陣型 (1 MA)
    2. 升級 步兵 A ➔ 步兵 I x 1 (1 MA)
    3. 建造 砲兵 II x 1 (1 MA)
    這就是演算法幫你找到的最優解！

---

# TTA Military Optimizer ⚔️ (English)

As enthusiasts of this wonderful game, my friends and I created a tool to calculate the maximum potential military strength and the optimal action sequence. In *Through the Ages*, finding the best combination of building and upgrading units to match a tactic—constrained by **Military Actions (MA)**, **Minerals**, and **Idle Population**—can be a brain-burner.

This tool uses a highly optimized **Backtracking DFS algorithm** to instantly solve for the maximum possible strength and outputs the exact sequence of actions with MA costs to achieve it. It features visual tactic selection and fully supports Antiquated Tactic calculations. The UI is also highly optimized for touch devices with stepper buttons.

It is fully responsive and strictly client-side, allowing you to run it in any web browser or save it to your device's home screen as a standalone web app. It supports both Traditional Chinese (TW) and English (EN).

## 💡 How to Use & Variables

*   **Available Resources:** 
    *   **Military Actions (MA):** The red tokens you have available.
    *   **Minerals:** Your current minerals.
    *   **Idle Pop:** Your available yellow tokens (required for building new units, but not for upgrading). Default is 99, assuming unlimited pop.
*   **Target Tactic & Source:** Click the tactic image you want to form (requires placing images in the `tactic/` folder). Specify if it is already active (costs 0 MA), in your hand (costs 1 MA), or common (costs 2 MA).
*   **Current Units:** Enter the count of your existing units across different ages. The grid is organized visually to match player intuition (Artillery-Cavalry-Infantry, sorted from Age III down to Age A). Default values are all 0.

### 📝 Examples (EN)

> You are in Age II and want to play the **"Napoleonic (1 Inf, 1 Cav, 1 Art)"** tactic from your hand.
> You have: **5 MAs, 12 Minerals, and 2 Idle Pop**.
> Your current army consists of: **2 Inf A** and **1 Cav I**.
> What is the absolute best way to spend your resources this turn?

*   **How to input:**
    *   Resources: 5 MA, 12 Mins, 2 Pop
    *   Tactic: Click the `Napoleonic` image, Source: `From Hand (1 MA)`
    *   Units: Inf A (Row A, Right col) = `2`, Cav I (Row I, Mid col) = `1`
*   **Result:** Click calculate, and the algorithm will instantly give you your max potential strength, break down the source `(Base Str 6 + Tactic Bonus 7)`, and give you the sequence:
    1. Play Tactic from Hand (1 MA)
    2. Upgrade Inf A ➔ Inf I x 1 (1 MA)
    3. Build Art II x 1 (1 MA)
    This takes the guesswork completely out of your turn!
