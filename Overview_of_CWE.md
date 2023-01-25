# CWE (Common Weakness Enumeration) 概要

## 目次
  1. CWE ( Common Weakness Enumeration ) とは
  2. CWE - 歴史 -
  3. CWE - タイプの分類 -
  4. CWE - 選択方針 -
  - 補足情報 - セキュリティ設定共通化手順SCAP -
  - 参照情報

## １．CWE ( Common Weakness Enumeration ) とは

  * MITRE がCVE開発の一環として、共通のソフトウェアの弱点を定義するために仕様策定し、2006年3月に原案を公開[^1]
  * CWE の主な活用方法および目論見(goal)[^2]
    - 製品の弱点を共通の言語で表現し、議論する
    - 既存製品の弱点をチェックする
    - 弱点の特定、緩和、防止に共通のベースラインとして活用する
    - 製品導入前に脆弱性の発生を防止する

  * 現在の[最新バージョン](https://cwe.mitre.org/data/)
    - 2022年10月リリースのバージョン 4.9 では、CWE の Weakness数 933個

  * [参考] IPA Webサイト[^3] での説明
    - 共通脆弱性タイプ一覧
    - ソフトウェアにおけるセキュリティ上の弱点(脆弱性)の種類を識別するための共通基準

## ２．CWE - 歴史 -

  1999年	CVE開発の一環でソフトウェアの弱点を定義するための仕様策定を開始

  2006年	原案を公開

  2008年	バージョン1.0 公開 

  2011年	バージョン2.0 公開

  2013年	バージョン2.5 公開、モバイルアプリケーションに関するCWEリスト (View ID:919) 追加

  2015年	バージョン2.9 公開、簡易化されたCWEリスト (View ID:1003) 追加

  2017年	バージョン3.0 公開

  2020年	バージョン4.0 公開、ハードウェアに関するCWEリスト (View ID:1194) 追加

## ３．CWE - タイプ[^4]の分類 -

CWE-(数字)で表現し、下表のタイプに分類される

|  タイプ  |    概要   | CWE の一例 |
| :-      | :-       | :-        |
|   View   | - 特定の観点から CWE を選択して集めたもの<br/>- CVE に割り当てない<br/>- 全47個*| CWE-699：ソフトウェア関連リスト<br/>CWE-1194：ハードウェア関連リスト<br/>CWE-1387：Top 25リスト |
| Category | - 共通の特性を持つ CWE をグループ化したもの<br/>- CVE に割り当てない<br/>- 全352個* | CWE-16：環境設定<br/>CWE-189：数値処理の問題<br/>CWE-264：許可・権限・アクセス制御 |
| Weakness | - 個々の脆弱性 (弱点) を表したもの<br/>- CVE に割り当てる<br/>- 全933個*<br/><br/>- Abstraction(抽象度)が高い順に4種類存在する: Pillar, Class, Base, Variant<br/>- 上記4種類以外にも複数要因が複合した表現もある: Compound<br/> | CWE-284 (Pillar)：アクセス制御不備<br/>CWE-20 (Class)：不適切な入力確認<br/>CWE-79 (Base)：XSS<br/>CWE-416 (Variant)：解放済みメモリの使用<br/>CWE-352 (Compound)：CSRF |

&#42; バージョン4.9 での個数


## ４．CWE - 選択方針[^5] -

脆弱性情報に適切な CWE を選択する方法の一例を示す

１．下記サイトで関連キーワードから検討する<br/>
　　https://cwe.mitre.org/find/

２．用途や製品分類に適した View から検討する
- 簡略化された View 1003：https://cwe.mitre.org/data/definitions/1003.html<br/>NVD (National Vulnerability Database ) などでも使用される[^6]
- ソフトウェア開発向けの View 699：https://cwe.mitre.org/data/definitions/699.html
- ハードウェア設計向けの View 1194：https://cwe.mitre.org/data/definitions/1194.html

３．CWE の親子関係から適切なものを検討する<br/>
　類似の CWE で迷った場合、下記サイトから親-子-孫などの関係を視覚的に確認する<br/>
　https://cwe.mitre.org/data/pdfs.html

４．その他留意点
- 脆弱性の影響（DoSなど）ではなく、根本的な原因・弱点を意識する
- 可能な限り Weakness の Abstraction(抽象度)が低いものを割り当てる
- CWE の用語[^7]をよく理解、正しく解釈する（以下は一例）
```
  Improper ： 「Missing」や「Incorrect」という挙動をカバーする用語
  Missing    ： 開発者が意図しない動作を説明する
  Incorrect  ： 動作するが、正しく実行しなかった場合を説明する
```
- 経験・ノウハウが必要なため、他人と意見をすり合わせることも重要

## 補足情報 - セキュリティ設定共通化手順SCAP[^8] -
NIST で情報セキュリティ対策の自動化と標準化をめざして開発されたもの

| 略称 | 正式名称 | 概要 |
| -   | -       | -   |
| CVE | Common Vulnerabilities and Exposures | 脆弱性を識別する |
| CCE | Common Configuration Enumeration | セキュリティ設定項目を識別する |
| CPE | Common Platform Enumeration | 脆弱性がある製品を識別する |
| CWE | Common Weakness Enumeration | 脆弱性を分類する |
| CVSS | Common Vulnerability Scoring System | 脆弱性の深刻度を評価する |
| XCCDF | Extensible Configuration Checklist Description Format | セキュリティ設定のチェックリストを記述する |
| OVAL | Open Vulnerability and Assessment Language | 脆弱性、セキュリティ設定をチェックするための言語 |

## 参照情報
[^1]: MITRE<br/>CWE - Common Weakness Enumeration<br/>https://cwe.mitre.org/

[^2]: MITRE<br/>CWE - About - CWE Overview<br/>https://cwe.mitre.org/about/

[^3]: IPA 独立行政法人 情報処理推進機構<br/>共通脆弱性タイプ一覧CWE概説<br/>https://www.ipa.go.jp/security/vuln/CWE.html

[^4]: MITRE<br/>CWE - Frequently Asked Questions (FAQ)<br/>https://cwe.mitre.org/about/faq.html#cwe_list_icons_key

[^5]: MITRE<br/>CWE - CWE Mapping Guidance<br/>https://cwe.mitre.org/documents/cwe_usage/guidance.html

[^6]: NIST<br/>NVD - Categories<br/>https://nvd.nist.gov/vuln/categories

[^7]: MITRE<br/>CWE - CWE Mapping Guidance - Common Terms Cheatsheet<br/>https://cwe.mitre.org/documents/cwe_usage/common_terms_cheatsheet.html

[^8]: IPA 独立行政法人 情報処理推進機構<br/>セキュリティ設定共通化手順SCAP概説<br/>https://www.ipa.go.jp/security/vuln/SCAP.html
