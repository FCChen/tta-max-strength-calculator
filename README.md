# TTA Military Optimizer (歷史巨輪 軍力最佳化計算機) ⚔️
*(Scroll down for English version)*

這是一個專為知名桌遊《歷史巨輪 (Through the Ages)》設計的輔助工具。在遊戲中，為了湊出最強的陣型，往往需要精算手中的**軍事行動點 (MA)**、**礦物** 以及 **閒置人口** 來決定哪些部隊該建造、哪些該升級。

本工具具備以下特點：
*   **視覺化陣型選擇**：整合了實際的卡牌圖片，直接點擊圖片即可選擇目標陣型。
*   **精準規則對應**：收錄所有 Age I ~ Age III 陣型（包含輕騎兵「2+騎兵等級」等特殊武力計算）。
*   **演算法最佳化**：採用 **Backtracking DFS 演算法**，能在毫秒內算出在給定資源下的「最大潛在武力」，並直接列出最省資源的「最佳行動順序」。

本工具無伺服器後端，純前端運作，您可以直接使用手機或 iPad 的瀏覽器開啟，並加入主畫面當作 Web App 使用。支援繁體中文 (TW) 與英文 (EN)。

## ⚙️ 圖片設定 (重要)
為了讓陣型選擇器正常顯示圖片，**請務必確保您將名為 `image_2bf93b.jpg` 的圖片檔案，與 `index.html` 放置在同一個 GitHub 目錄下**。系統會使用 CSS Sprite 技術自動為您裁切圖片。

## 💡 使用說明與變數定義

*   **可用資源:** 
    *   **軍事行動點 (MA):** 你這回合可以用的紅點數量。
    *   **礦物 (Minerals):** 你現有的礦物數量。
    *   **閒置人口 (Pop):** 你擁有的黃色工人數量（建造新部隊必備，升級部隊則不需要）。
*   **目標陣型 & 來源:** 點選卡牌圖片選擇你想湊成的陣型。如果該陣型已經在你場上，選擇「已在場上 (0 MA)」。如果要從手上打出，會自動扣除 1 MA；複製別人的會自動扣除 2 MA。
*   **現有兵種數量:** 依照表格（從 III 時代到 A 時代，由左至右為 砲兵、騎兵、步兵），填入你場上各兵種目前的數量。

### 📝 實戰範例 (TW)

> 你現在在 Age II (二時代)，你想打出手上的**「拿破崙 (1步 1騎 1砲)」**陣型。
> 你的資源有：**5 MA、12 礦物、2 個閒置人口**。
> 你場上目前只有：**2 個步兵 A** 和 **1 個騎兵 I**。
> 你想知道怎麼做才能極大化這回合的武力？

*   **操作方式：**
    *   資源輸入：5 MA, 12 礦, 2 人口
    *   點選圖片陣型：選擇 `拿破崙`
    *   來源選擇：`從手中打出 (1 MA)`
    *   部隊輸入：步兵 A = `2`，騎兵 I = `1`
*   **結果：** 點擊計算，系統會瞬間告訴你潛在的最大武力，以及你應該：
    1. 打出手中陣型 (1 MA)
    2. 升級 1 個 Inf A ➔ Inf I
    3. 建造 1 個 Art II
    這就是演算法幫你找到的最優解！

---

# TTA Military Optimizer ⚔️ (English)

As enthusiasts of this wonderful game, my friends and I created a tool to calculate the maximum potential military strength and the optimal action sequence. In *Through the Ages*, finding the best combination of building and upgrading units to match a tactic—constrained by **Military Actions (MA)**, **Minerals**, and **Idle Population**—can be a brain-burner.

Key features include:
*   **Visual Tactic Selector:** Uses actual card images via CSS sprites for intuitive selection.
*   **Accurate Ruleset:** Fully supports Age I ~ Age III tactics, including complex formulas like the Hussars (Level-based bonuses).
*   **Algorithmic Optimization:** Uses a highly optimized **Backtracking DFS algorithm** to instantly solve for the maximum possible strength.

It is fully responsive and strictly client-side, allowing you to run it in any web browser or save it to your device's home screen as a standalone web app. It supports both Traditional Chinese (TW) and English (EN).

## ⚙️ Image Setup (Important)
For the visual tactic selector to work, **ensure the image file named `image_2bf93b.jpg` is placed in the same directory as `index.html` on your GitHub repository**. The tool uses CSS sprites to automatically crop the image for each button.

## 💡 How to Use & Variables

*   **Available Resources:** 
    *   **Military Actions (MA):** The red tokens you have available.
    *   **Minerals:** Your current minerals.
    *   **Idle Pop:** Your available yellow tokens (required for building new units, but not for upgrading).
*   **Target Tactic & Source:** Click on the card image to select the tactic you want to form. Specify if it is already active (costs 0 MA), in your hand (costs 1 MA), or common (costs 2 MA).
*   **Current Units:** Enter the count of your existing units in the grid (ordered from Age III down to Age A, with Artillery, Cavalry, and Infantry from left to right).

### 📝 Examples (EN)

> You are in Age II and want to play the **"Napoleonic (1 Inf, 1 Cav, 1 Art)"** tactic from your hand.
> You have: **5 MAs, 12 Minerals, and 2 Idle Pop**.
> Your current army consists of: **2 Inf A** and **1 Cav I**.
> What is the absolute best way to spend your resources this turn?

*   **How to input:**
    *   Resources: 5 MA, 12 Mins, 2 Pop
    *   Select Tactic Image: `Napoleonic`
    *   Source: `From Hand (1 MA)`
    *   Units: Inf A = `2`, Cav I = `1`
*   **Result:** Click calculate, and the algorithm will instantly give you your max potential strength and the optimal sequence:
    1. Play Tactic from Hand (1 MA)
    2. Upgrade Inf A ➔ Inf I
    3. Build Art II
    This takes the guesswork completely out of your turn!
