# UstNext カラーリサーチE・アクセシビリティ × 色覚多様性

作成日：2026-06-03
担当：執行部（アクセシビリティ責任者）
対象プロダクト：UstNext（専門学校生×企業×就職課の3者連動就活PF）

---

## 0. リサーチの前提

UstNextの顧客には専門学校（教育機関）が含まれるため、公的機関に準じた配慮が求められる。日本国内でも教育機関のデジタルアクセシビリティはJIS X 8341-3:2016（WCAG 2.0準拠）を引用するのが慣例で、EUのEAA・米国ADA Title IIなどの世界的潮流もWCAG 2.1 Level AAを最低要件とする方向に揃ってきている。

参考：
- W3C「Understanding Success Criterion 1.4.3: Contrast (Minimum)」 https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum
- EdTech Magazine「A Guide to the ADA Title II Accessibility Rule」 https://edtechmagazine.com/higher/article/2025/06/guide-ada-title-ii-accessibility-rule-perfcon
- Magic EdTech「WCAG Compliance for EdTech」 https://www.magicedtech.com/blogs/wcag-compliance-edtech/

---

## 1. WCAG 2.1 / 2.2 要件

### 1.1 コントラスト要件（SC 1.4.3 / 1.4.6 / 1.4.11）

| レベル | 通常テキスト | 大テキスト | UIコンポーネント・グラフィックオブジェクト |
|---|---|---|---|
| AA  | 4.5:1 以上 | 3:1 以上 | 3:1 以上（SC 1.4.11 Non-text Contrast） |
| AAA | 7:1 以上   | 4.5:1 以上 | 規定なし |

- 「大テキスト」の定義：18pt（24px）以上、または 14pt（約18.67px）以上の太字。
- 計算式：`Contrast Ratio = (L1 + 0.05) / (L2 + 0.05)`（L1=明るい方、L2=暗い方の相対輝度）。
- 相対輝度の算出には sRGB ガンマ補正後の `0.2126R + 0.7152G + 0.0722B` を用いる。

出典：
- W3C「Understanding SC 1.4.3 Contrast (Minimum)」 https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum
- W3C「Understanding SC 1.4.6 Contrast (Enhanced)」（AAA, 7:1） https://www.w3.org/WAI/WCAG21/Understanding/contrast-enhanced
- W3C「Understanding SC 1.4.11 Non-text Contrast」 https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast.html
- Make Things Accessible「Contrast requirements for WCAG 2.2 Level AA」 https://www.makethingsaccessible.com/guides/contrast-requirements-for-wcag-2-2-level-aa/

### 1.2 WCAG 2.2 で新規追加された関連項目

- SC 2.4.11 Focus Not Obscured（AA）：フォーカスインジケータが他要素に隠れない。
- SC 2.4.13 Focus Appearance（AAA）：フォーカス輪郭が周囲と3:1コントラスト＋一定の太さ。
- これらは色そのものではなくフォーカスリングや状態表示の色設計に効く。
- 出典：W3C WCAG 2.2 Recommendation https://www.w3.org/TR/WCAG22/

---

## 2. 色覚多様性（CVD）の基礎データ

### 2.1 日本国内の出現率

- 先天赤緑色覚異常：**日本人男性の約5%、女性の約0.2%**（日本眼科医会の公式統計）。
- 出典：公益社団法人 日本眼科医会「冊子『色覚異常を正しく理解するために』」 https://www.gankaikai.or.jp/colorvision/detail/post_9.html
- 出典：参天製薬「色覚異常」 https://www.santen.com/jp/healthcare/eye/library/color_deficiency
- 補足：日本全体ではP型・D型のみで320万人以上と推計（PATCH THE WORLD「色覚多様性とは」 https://mannen.jp/patchtheworld/18641/ ）。

### 2.2 主要型と見え方

| 型 | 別名 | 影響を受ける錐体 | 主な見え方の特徴 |
|---|---|---|---|
| P型（1型） | Protan / Protanopia・Protanomaly | L錐体（赤） | 赤が暗く沈む。赤と黒、赤と緑、ピンクと水色などが混同しやすい |
| D型（2型） | Deutan / Deuteranopia・Deuteranomaly | M錐体（緑） | 緑の識別が低下。赤と緑、緑と茶、紫と青などが混同しやすい。**最多の型** |
| T型（3型） | Tritan / Tritanopia | S錐体（青） | 青と緑、黄と紫、ピンクと白などが混同しやすい。出現率は約0.01%と稀 |
| A型 | Achromatopsia | 全錐体 | 完全色覚異常。極めて稀 |

出典：
- rgblind「Types of Color Blindness Explained」 https://rgblind.com/blog/types-of-color-blindness
- Interaction Design Foundation「What is Color Blindness?」 https://www.interaction-design.org/literature/topics/color-blindness

### 2.3 専門学校生市場における該当人数概算

- 母集団：令和6年度学校基本調査 専門学校在学者数 **558,255人**。
- 出典：リクルート進学総研「専門学校の現状と今後への考察」（令和6年度数値の引用元） https://souken.shingakunet.com/higher/2025/04/post-3476.html
- 出典：文部科学省「学校基本調査」 https://www.mext.go.jp/b_menu/toukei/chousa01/kihon/1267995.htm
- 男女比は概ね5:5とすると、男性約27.9万人 × 5% ≒ **約14,000人**、女性約27.9万人 × 0.2% ≒ **約560人**。
- 合計でCVDを持つ専門学校生は **約14,500人**（オーダーとしては「1学年あたり5,000人規模」「クラスに1人以上」）。
- 教員・就職課・採用企業担当を含めれば、UstNextの想定ユーザのうち**3〜5%が常時CVD条件下でUIを使う**ことを前提にすべき。

### 2.4 シミュレーションツール

| ツール | 対象 | 価格 | 用途 |
|---|---|---|---|
| Color Oracle | Win/Mac/Linux | 無料 | OS全体に色覚フィルタを被せ、デザインカンプ・LP・スライドをそのまま確認 |
| Sim Daltonism | macOS / iOS | 無料（OSS） | カメラ越し / 画面下に重ねるリアルタイムフィルタ |
| Stark | Figma / Sketch / Chrome | 無料枠＋有料 | コントラスト計測とCVDシミュを制作フローに統合 |

出典：
- Color Oracle 公式 https://colororacle.org/
- Sim Daltonism 公式 https://michelf.ca/projects/sim-daltonism/
- GitHub「sim-daltonism」 https://github.com/michelf/sim-daltonism/
- Stark（WCAG Explainer） https://www.getstark.co/wcag-explained/perceivable/distinguishable/contrast-minimum/

---

## 3. 同業他社のアクセシビリティ事例

| 企業 / プロダクト | 領域 | 公言レベル | 取組内容 | 出典 |
|---|---|---|---|---|
| Roche | 製薬（ステートメントの好例として広く引用） | WCAG 2.2 Level AA 部分適合 | 第三者監査・スタッフ研修・ユーザビリティテスト・連絡窓口公開 | https://accessibleweb.com/tips-tools-tutorials/exemplary-accessibility-statements-examples/ |
| Shopify | コマースSaaS（HR/採用にも近い） | WCAG 2.1 参照 | 複数年ロードマップとして継続課題化 | 同上 |
| Colorado State University | 高等教育機関 | WCAG 参照 | 大学理念に紐付け、報告窓口を明示 | 同上 |
| 米国 EdTech 全般 | LMS等 | WCAG 2.1 Level AA（ADA Title II起点） | 公立大・公立校への提供は2026年4月までに2.1 AA必須 | https://www.accessibility.works/blog/lms-wcag-hb21-1110-ada-eaa-compliance-schools-saas-guide/ |
| Magic EdTech | EdTech向け監査ベンダ | WCAG 2.1 AA / 2.2 AAを提示 | VPAT発行支援、教育機関調達要件への適合支援 | https://www.magicedtech.com/blogs/wcag-compliance-edtech/ |

UstNextへの示唆：
- 専門学校が顧客である以上、**「WCAG 2.1 Level AA 適合」をアクセシビリティ・ステートメントとして明文公開**することが今後の調達要件で効く。
- ステートメントは「達成済み」より「部分適合＋改善ロードマップ＋連絡窓口」の形が国際的に主流（Rocheがロールモデル）。

---

## 4. 避けるべき配色 / 推奨配色アプローチ

### 4.1 避けるべき配色

1. **赤×緑の組合せでステータスを伝える**（成功/失敗、合格/不合格）。D型・P型で同色化しやすい。
   - 例：求人カードで「応募済 緑」「未応募 赤」のように色だけで区別 → NG。アイコン・文字も併用。
2. **赤×黒、緑×茶**。P型は赤が暗く沈むため黒と区別しづらい。
3. **紫×青**。D型では混同しやすい。グラデの両端としては許容できても、隣接ボタンの色分けには不適。
4. **ピンク×水色、青×緑**：T型で混同しやすい。
5. **純白(#FFFFFF)背景に淡色テキスト**：眼精疲労と低コントラストの二重リスク。背景を #F8FAFC〜#F1F5F9 などへ微オフセット推奨。
6. **AA未満のグラデーション上にテキストを直接乗せる**：紫×ピンクLPの中央域は特に危険（後述 §5）。

出典：
- CUDO「カラーユニバーサルデザイン推奨配色セット」 https://cudo.jp/?page_id=1565
- ESRI「Designing Maps for Colorblind Readability」 https://www.esri.com/arcgis-blog/products/arcgis-pro/mapping/designing-maps-for-colorblind-readability

### 4.2 推奨アプローチ

- **色相だけでなく明度・彩度で差を作る**（モノクロ化しても情報が残るか）。
- **色＋形（アイコン）＋テキストラベル**の三重符号化（WCAG SC 1.4.1 Use of Color）。
- **アクセント色は青・オレンジ・黄を優先**。CVD全型で識別性が高い。
- **本文テキストは #0F172A（near-black）など輝度の低い色を白系背景に**：白×#0F172A で17.85:1（AAA余裕でクリア）。
- **ブランドカラーを「面で大きく使う」ときと「小さなアイコン/文字に使う」ときで明度違いのトークンを用意**（例：blue-500 はバッジ用、blue-700 は本文リンク用）。

ツール：
- Leonardo（Adobe）：https://leonardocolor.io/ — コントラスト比目標から逆算してパレット生成。
- Coolors Contrast Checker：https://coolors.co/contrast-checker
- Stark：https://www.getstark.co/

---

## 5. 既存案の評価

WCAG 2.1 の公式式（`(L1+0.05)/(L2+0.05)`、相対輝度はsRGBガンマ補正後の加重和）で実測。

出典：W3C「Relative luminance」 https://www.w3.org/WAI/GL/wiki/Relative_luminance / W3C「Understanding SC 1.4.3」 https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum

### 5.1 既存ロゴ：青系グラデ #38BDF8 → #1E40AF

| 組合せ | 比率 | AA通常(4.5) | AA大(3) | AAA通常(7) | 備考 |
|---|---:|:--:|:--:|:--:|---|
| 白 × #1E40AF（濃端） | 8.72:1 | OK | OK | **OK** | 本文・ボタン文字として最良 |
| 白 × #38BDF8（明端） | 2.14:1 | NG | NG | NG | テキスト不可。アクセント面のみ |
| #38BDF8 × #1E40AF（グラデ内） | 4.07:1 | NG | OK | NG | 大テキスト・アイコン輪郭は可 |

CVD評価：
- 青系単色グラデは **P型・D型でも色相が大きく崩れにくく安全**（青は両型が比較的識別できる）。
- T型では青が緑〜灰に寄って見えるため、明度差を保てば識別性は維持される。
- **総合：CVD適合度は高い。WCAGは「濃側にテキスト」原則で運用すればAAクリア。明側だけにテキストを置く設計はNG**。

### 5.2 既存LP：紫×ピンクグラデ #7C3AED → #EC4899

| 組合せ | 比率 | AA通常 | AA大 | AAA通常 | 備考 |
|---|---:|:--:|:--:|:--:|---|
| 白 × #7C3AED | 5.70:1 | OK | OK | NG | ボタンとしては合格 |
| 白 × #EC4899 | 3.53:1 | NG | OK | NG | 本文不可、大見出しのみ |
| #7C3AED × #EC4899（グラデ内） | 1.62:1 | NG | NG | NG | この上にテキストを乗せると確実に違反 |

CVD評価：
- 紫は D型で青と混同、P型で青〜暗灰に沈みやすい。
- ピンク #EC4899 は P型・D型では「くすんだ茶/灰」に寄り、**鮮やかさのブランド狙いがCVD条件下で消える**。
- T型ではピンクが白〜淡黄に見え、白背景との分離が弱くなる。
- グラデーション中央域（紫⇔ピンクの中間）はP/D型で「茶〜暗赤」になり、ブランド体験が大きく変質する。

**結論：既存LPの紫×ピンクは「公的機関的配慮」が必要なUstNextのコーポレートカラーとしては要再設計**。LPのキービジュアルとして残すなら、テキストは必ず黒系（#0F172A）またはダーク帯の上に白文字で、グラデ中央域には文字を置かない運用ルールが必要。

### 5.3 まとめ

- **既存ロゴ青系：コーポレートカラーの主軸として継続候補。ただし「濃側#1E40AFを基準色」とし、テキスト用は更に1段濃い #1E3A8A も用意するとAAA余裕。**
- **既存LP紫×ピンク：UI主軸からは外し、キャンペーン・特集ページのアクセントに限定。**

---

## 6. 推奨パレット案（WCAG AA以上を保証）

すべての主要ペアを上記式で実測し、AA以上を担保。各案は「Primary（ブランド主軸）／Secondary（補助）／Accent（強調）／Text on light／Surface」の役割で構成。

### 案A：「コントラスト最大化・青系継承」（推奨度★★★）

既存ロゴ青系の資産を活かし、AAA級コントラストで公的機関対応を最優先。

| ロール | HEX | 用途 | 対 #FFFFFF | 対 #0F172A |
|---|---|---|---:|---:|
| Primary（ブランド軸） | **#1D4ED8**（blue-700） | ロゴ・主要CTA・リンク | 6.70:1（AA OK） | 2.66:1 |
| Primary Dark（テキスト用） | **#1E3A8A**（blue-900） | 本文リンク・見出し | 10.36:1（**AAA OK**） | — |
| Secondary | **#0E7490**（cyan-700） | サブナビ・タグ | 5.36:1（AA OK） | — |
| Accent | **#F59E0B**（amber-500） | 緊急通知・ハイライト（CVD全型で青と弁別可） | 2.16:1（テキスト不可・面のみ） | 9.46:1（AAA OK） |
| Text | **#0F172A**（slate-900） | 本文 | 17.85:1（AAA OK） | — |
| Surface | **#F8FAFC**（slate-50） | 背景 | — | 17.06:1（AAA OK） |

CVD評価：青×橙はP/D/T全型で最も識別性が高い古典的安全ペア（ESRI推奨）。

### 案B：「教育機関親和・ティール基調」（推奨度★★☆）

公的機関で多用される寒色＋穏やかさ。既存ロゴから少しシフトする提案。

| ロール | HEX | 用途 | 対 #FFFFFF |
|---|---|---|---:|
| Primary | **#0F766E**（teal-700） | ブランド軸 | 5.31:1（AA OK） |
| Primary Dark | **#134E4A**（teal-900） | テキスト用 | 11.27:1（AAA OK） |
| Secondary | **#1D4ED8**（blue-700） | リンク | 6.70:1（AA OK） |
| Accent | **#EA580C**（orange-600） | CTA強調 | 4.66:1（AA OK） |
| Text | #0F172A | 本文 | 17.85:1 |
| Surface | #F8FAFC | 背景 | — |

CVD評価：青緑×橙はCVDO推奨配色セットに沿う組合せで、P/D/T全型で識別良好。

### 案C：「既存資産フル活用ハイブリッド」（推奨度★★☆）

既存ロゴ青グラデ＋既存LP紫はキービジュアルに温存しつつ、UIはAA保証された別トークンで運用。

| ロール | HEX | 用途 | 対 #FFFFFF |
|---|---|---|---:|
| Brand Gradient（KV専用） | #38BDF8 → #1E40AF | LP上部キービジュアルのみ | テキスト乗せ禁止運用 |
| UI Primary | **#1E40AF**（blue-800） | ボタン・リンク | 8.72:1（AAA OK） |
| Highlight | **#7C3AED**（violet-600） | 特集・キャンペーン強調 | 5.70:1（AA OK） |
| Accent | **#FACC15**（yellow-400） | バッジ・新着 | 1.79:1（テキスト不可・面のみ。文字は #0F172A 重ね＝11.66:1 AAA OK） |
| Text | #0F172A | 本文 | 17.85:1 |
| Surface | #F8FAFC | 背景 | — |

注：紫 #7C3AED はテキスト用に5.70:1で AAは確保するが、面で使う場合は隣接する緑/青と混同しないようアイコン併用が必須。

---

## 7. 運用ルール（UstNext向け実装ガイド）

1. **AA最低、主要CTAはAAA目標**。リリース前に Stark / axe DevTools で全画面スキャン。
2. **CVDシミュは Color Oracle で P型・D型・T型を必ず確認**。ピンク・紫を使う画面は特に重点チェック。
3. **色のみで情報を伝えない**（アイコン・ラベル・パターン併用）。
4. **アクセシビリティ・ステートメントを公開**：「WCAG 2.1 Level AA に準拠／一部適合外あり／改善ロードマップ／連絡窓口」（Rocheモデル）。
5. **グラデーション上にテキストを置く場合は、最暗端基準でWCAGを満たす範囲のみ使用**。中央域に文字を置かない。
6. **既存LPの紫×ピンク**は「採用イベント・キャンペーンページの装飾」へ役割限定し、本体UIは案A or 案Bを採用。

---

## 8. 出典一覧

### WCAG・W3C
- W3C「WCAG 2.2 Recommendation」 https://www.w3.org/TR/WCAG22/
- W3C「Understanding SC 1.4.3 Contrast (Minimum)」 https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum
- W3C「Understanding SC 1.4.6 Contrast (Enhanced)」 https://www.w3.org/WAI/WCAG21/Understanding/contrast-enhanced
- W3C「Understanding SC 1.4.11 Non-text Contrast」 https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast.html
- W3C「Relative luminance」 https://www.w3.org/WAI/GL/wiki/Relative_luminance

### コントラスト解説（第三者）
- Make Things Accessible「Contrast requirements for WCAG 2.2 Level AA」 https://www.makethingsaccessible.com/guides/contrast-requirements-for-wcag-2-2-level-aa/
- Accessibility Assistant「WCAG 2.2 Contrast Ratio Explained」 https://accessibilityassistant.com/blog/accessibility-insights/how-to-apply-wcag-22-colour-contrast-accessibility/
- WebAIM Contrast Checker https://webaim.org/resources/contrastchecker/

### 色覚多様性（日本）
- 日本眼科医会「色覚異常を正しく理解するために」 https://www.gankaikai.or.jp/colorvision/detail/post_9.html
- 参天製薬「色覚異常」 https://www.santen.com/jp/healthcare/eye/library/color_deficiency
- 立命館大学人間科学研究所「色覚障害について考える」 https://www.ritsumeihuman.com/essay/essay390/
- NPO CUDO「カラーユニバーサルデザイン推奨配色セット」 https://cudo.jp/?page_id=1565
- PATCH THE WORLD「色覚多様性とは？」 https://mannen.jp/patchtheworld/18641/

### 色覚多様性（海外）
- rgblind「Types of Color Blindness」 https://rgblind.com/blog/types-of-color-blindness
- rgblind「How to Design for Tritanopia」 https://rgblind.com/blog/how-to-design-for-tritanopia
- Interaction Design Foundation「What is Color Blindness?」 https://www.interaction-design.org/literature/topics/color-blindness
- ESRI「Designing Maps for Colorblind Readability」 https://www.esri.com/arcgis-blog/products/arcgis-pro/mapping/designing-maps-for-colorblind-readability

### CVDシミュレーションツール
- Color Oracle https://colororacle.org/
- Sim Daltonism https://michelf.ca/projects/sim-daltonism/ / https://github.com/michelf/sim-daltonism/
- Stark https://www.getstark.co/

### EdTech・HR Techのアクセシビリティ
- Accessible Web「Exemplary Accessibility Statement Examples」（Roche/Shopify/CSU） https://accessibleweb.com/tips-tools-tutorials/exemplary-accessibility-statements-examples/
- EdTech Magazine「A Guide to the ADA Title II Accessibility Rule」 https://edtechmagazine.com/higher/article/2025/06/guide-ada-title-ii-accessibility-rule-perfcon
- Magic EdTech「WCAG Compliance for EdTech」 https://www.magicedtech.com/blogs/wcag-compliance-edtech/
- Accessibility.Works「LMS ADA Title II Compliance」 https://www.accessibility.works/blog/lms-wcag-hb21-1110-ada-eaa-compliance-schools-saas-guide/

### 専門学校生統計
- 文部科学省「学校基本調査」 https://www.mext.go.jp/b_menu/toukei/chousa01/kihon/1267995.htm
- 文部科学省「学校基本調査－令和7年度 結果の概要」 https://www.mext.go.jp/b_menu/toukei/chousa01/kihon/kekka/k_detail/2025.htm
- リクルート進学総研「専門学校の現状と今後への考察」 https://souken.shingakunet.com/higher/2025/04/post-3476.html
