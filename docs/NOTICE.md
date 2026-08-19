# 辞書データのライセンス条文 (NOTICE)

Roman が同梱する変換辞書に適用されるライセンスの**条文原文**。 辞書データを再配布する場合は、**本ファイルの条文をデータと共に保持すること**が条件となる。 本ファイルは配布物 (.pkg) にも `docs/NOTICE.md` として同梱される。

最終確認: 2026-08-10(v1.0 の同梱辞書に基づく)。 コンポーネント全体のライセンス一覧は [LICENSES.md](LICENSES.md) を参照。

下記の条文はいずれも mozc OSS 辞書 ([google/mozc](https://github.com/google/mozc)) に由来する。 IPAdic (NAIST)・ICOT・沖縄辞書の条文は mozc の [LICENSE](https://github.com/google/mozc/blob/master/LICENSE) と [src/data/dictionary_oss/README.txt](https://github.com/google/mozc/blob/ed4a62b006eb/src/data/dictionary_oss/README.txt) の両方に同一内容で記載されているため、ここでは1回のみ掲載する。

## 本ファイルが対象とする同梱ファイル

配布物内の `server/dict/` 配下。各ファイルの抽出条件は開発用リポジトリに記録しており、本リポジトリには含まれない。下表に出自と適用条文をまとめる。

| ファイル | 内容 | 適用される条文 |
| --- | --- | --- |
| `mozc-lattice.tsv` | mozc OSS 辞書の全エントリ(読み→左ID:右ID:コスト:表記) | 下記 BSD-3-Clause ＋ IPAdic (NAIST) / ICOT ＋ 沖縄辞書 (PD) |
| `mozc-connection.bin` | 品詞IDペアの接続コスト行列 | 同上 |
| `mozc-pos.tsv` | mozc `id.def` の品詞ID→品詞名 | 同上 |
| `katakana-mozc.tsv` / `general.tsv` / `verbs.tsv` | 上記からの機械抽出(カタカナ最有力読み・一般名詞・動詞基本形) | 同上 |
| `kaomoji.tsv` | 顔文字(mozc `emoticon.tsv` 由来) | 上記 mozc 本体と同じ条文 |
| `org-names.tsv` | 組織名リスト(Wikidata 由来) | CC0 1.0(保持義務なし。下記参照) |
| `med-disease.tsv` | 病名・症状(万病辞書 由来) | CC BY 4.0(下記の帰属表示) |
| `katakana-drug.tsv` | 医薬品の成分名(厚生労働省の公表資料 由来) | 公共データ利用規約(第1.0版)(下記の出典表示) |
| `corp.tsv` | 上場会社名(金融庁 EDINET の公表資料 由来) | 公共データ利用規約(第1.0版)(下記の出典表示) |
| `idiom.tsv` | 慣用句・ことわざ・四字熟語(JMdict 由来) | CC BY-SA 4.0(下記の帰属表示) |
| `names-jmnedict.tsv` | 固有名詞 — 人物の姓名・地名・駅名・組織名・会社名(JMnedict 由来) | CC BY-SA 4.0(下記の帰属表示) |
| `katakana-it.tsv` / `extra.tsv` / `particles.tsv` / `noun-types.tsv` / 各 `*-deny.tsv` | 本プロジェクトで新規作成した語彙・規則リスト | 本プロジェクトに帰属(第三者条文の適用なし) |

なお、同梱する形態素解析器 kuromoji.js の辞書 mecab-ipadic-2.7.0 にも、下記 「IPAdic (NAIST) / ICOT Free Software」と**同一の条文**が適用される。 上流パッケージの `NOTICE.md` が配布物内 (`server/node_modules/kuromoji/`) に そのまま含まれている。

## mozc 本体 — BSD-3-Clause

```
Copyright 2010-2018, Google Inc.
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

  * Redistributions of source code must retain the above copyright
    notice, this list of conditions and the following disclaimer.
  * Redistributions in binary form must reproduce the above
    copyright notice, this list of conditions and the following disclaimer
    in the documentation and/or other materials provided with the
    distribution.
  * Neither the name of Google Inc. nor the names of its
    contributors may be used to endorse or promote products derived from
    this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

## 辞書エントリ — IPAdic (NAIST) / ICOT Free Software

mozc の `src/data/dictionary*` に適用される。語彙の大部分がこの条件下にある。

```
Copyright 2000, 2001, 2002, 2003 Nara Institute of Science
and Technology.  All Rights Reserved.

Use, reproduction, and distribution of this software is permitted.
Any copy of this software, whether in its original form or modified,
must include both the above copyright notice and the following
paragraphs.

Nara Institute of Science and Technology (NAIST),
the copyright holders, disclaims all warranties with regard to this
software, including all implied warranties of merchantability and
fitness, in no event shall NAIST be liable for
any special, indirect or consequential damages or any damages
whatsoever resulting from loss of use, data or profits, whether in an
action of contract, negligence or other tortuous action, arising out
of or in connection with the use or performance of this software.

A large portion of the dictionary entries
originate from ICOT Free Software.  The following conditions for ICOT
Free Software applies to the current dictionary as well.

Each User may also freely distribute the Program, whether in its
original form or modified, to any third party or parties, PROVIDED
that the provisions of Section 3 ("NO WARRANTY") will ALWAYS appear
on, or be attached to, the Program, which is distributed substantially
in the same form as set out herein and that such intended
distribution, if actually made, will neither violate or otherwise
contravene any of the laws and regulations of the countries having
jurisdiction over the User or the intended distribution itself.

NO WARRANTY

The program was produced on an experimental basis in the course of the
research and development conducted during the project and is provided
to users as so produced on an experimental basis.  Accordingly, the
program is provided without any warranty whatsoever, whether express,
implied, statutory or otherwise.  The term "warranty" used herein
includes, but is not limited to, any warranty of the quality,
performance, merchantability and fitness for a particular purpose of
the program and the nonexistence of any infringement or violation of
any right of any third party.

Each user of the program will agree and understand, and be deemed to
have agreed and understood, that there is no warranty whatsoever for
the program and, accordingly, the entire risk arising from or
otherwise connected with the program is assumed by the user.

Therefore, neither ICOT, the copyright holder, or any other
organization that participated in or was otherwise related to the
development of the program and their respective officials, directors,
officers and other employees shall be held liable for any and all
damages, including, without limitation, general, special, incidental
and consequential damages, arising out of or otherwise in connection
with the use or inability to use the program or any product, material
or result produced or otherwise obtained by using the program,
regardless of whether they have been advised of, or otherwise had
knowledge of, the possibility of such damages at any time during the
project or thereafter.  Each user will be deemed to have agreed to the
foregoing by his or her commencement of use of the program.  The term
"use" as used herein includes, but is not limited to, the use,
modification, copying and distribution of the program and the
production of secondary products from the program.

In the case where the program, whether in its original form or
modified, was distributed or delivered to or received by a user from
any person, organization or entity other than ICOT, unless it makes or
grants independently of ICOT any specific warranty to the user in
writing, such person, organization or entity, will also be exempted
from and not be held liable to the user for any such damages as noted
above as far as the program is concerned.
```

## 沖縄辞書 — Public Domain

mozc の `src/data/dictionary*` に含まれる、沖縄の地名・人名等の固有名詞データ ([makotoga/o-dic](https://github.com/makotoga/o-dic))。パブリックドメインのため保持義務は生じないが、 上流の宣言文をそのまま掲げる。

```
Public Domain Dataです。使用・変更・配布に関しては一切の制限をつけません。
商品などに組み込むことも自由に行なってください。すでにいくつかの辞書には沖縄辞書が採用されています。
勝手ながら、沖縄辞書に寄贈された辞書も in the Public Domain' 扱いとさせていただきます。
```

## 組織名リスト — CC0 1.0 (条文なし)

同梱する組織名リストの出典である [Wikidata](https://www.wikidata.org/) は CC0 1.0 Universal (パブリックドメイン) で著作権が放棄されており、**保持すべき条文は無い** (表示は謝意として記載)。

## 病名・症状リスト — CC BY 4.0 の帰属表示

配布物内の `server/dict/med-disease.tsv` に適用される。 CC BY 4.0 第3条(a)(1) が求める表示を以下に掲げる。同条(a)(1)(C) は 条文原文の同梱に代えて URI の提示を認めているため、条文は下記リンクで示す。

- **作品**: 万病辞書 (MANBYO_202106)
- **著作権者**: 奈良先端科学技術大学院大学 ソーシャル・コンピューティング研究室
- **出典**: https://sociocom.naist.jp/manbyou-dic/
- **ライセンス**: Creative Commons Attribution 4.0 International (CC BY 4.0)
- **条文**: https://creativecommons.org/licenses/by/4.0/legalcode.ja
- **参考文献**: J-MeDic: A Japanese Disease Name Dictionary based on Real Clinical Usage (LREC 2018)
- **改変の有無**: **改変している。** 信頼度レベル S・A の項目だけを採り、表記と「出現形よみ」を Roman の辞書形式(読み→コスト:表記)へ変換した。抽出条件は開発用リポジトリの `server/tools/extract-med.py` に記録している

CC BY 4.0 に share-alike 条項は無いため、Roman 本体および他の同梱物にこのライセンスは及ばない。

## 慣用句・ことわざリスト — CC BY-SA 4.0 の帰属表示

配布物内の `server/dict/idiom.tsv` に適用される。 この抽出物は JMdict の派生物であり、CC BY-SA 4.0 の share-alike 条項により**本ファイル自体も CC BY-SA 4.0 で配布される** (zenz と同じ扱い。[TERMS.md](../TERMS.md) 第3条の再配布・改変の禁止は第4条のとおり本ファイルには適用されない)。share-alike が及ぶのは本ファイルまでで、Roman 本体および他の同梱物には及ばない。

- **作品**: JMdict (Japanese-Multilingual Dictionary)
- **著作権者**: Electronic Dictionary Research and Development Group (EDRDG) / James William Breen
- **出典**: https://www.edrdg.org/jmdict/j_jmdict.html
- **ライセンス**: Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
- **利用許諾**: https://www.edrdg.org/edrdg/licence.html
- **条文**: https://creativecommons.org/licenses/by-sa/4.0/legalcode
- **改変の有無**: **改変している。** 慣用句・ことわざ・四字熟語のタグ (proverb / id / yoji) が付いたエントリだけを採り、表記と読み (reb) を Roman の辞書形式へ変換した。抽出条件は開発用リポジトリの `server/tools/extract-idiom.py` に記録している
- **元データの版**: JMdict 2026-08-11 生成版 (idiom.tsv の1行目に記録)
- **更新**: EDRDG の利用許諾 第4条は「最新版からの定期更新の手続き」を義務としている (WWW サーバの例示は月1回。守らないことはライセンス違反と明記されている)。Roman の手続き — **リリースビルド (release.sh) は、元データの生成日が90日より古いとビルドを中止する**。更新は JMdict_e.gz を再取得し extract-idiom.py を再実行する

## 固有名詞リスト — CC BY-SA 4.0 の帰属表示

配布物内の `server/dict/names-jmnedict.tsv` に適用される。 この抽出物は JMnedict の派生物であり、CC BY-SA 4.0 の share-alike 条項により**本ファイル自体も CC BY-SA 4.0 で配布される** (idiom.tsv と同じ扱い。[TERMS.md](../TERMS.md) 第3条の再配布・改変の禁止は第4条のとおり本ファイルには適用されない)。share-alike が及ぶのは本ファイルまでで、Roman 本体および他の同梱物には及ばない。

- **作品**: JMnedict (Japanese Multilingual Named Entity Dictionary / ENAMDICT)
- **著作権者**: Electronic Dictionary Research and Development Group (EDRDG) / James William Breen
- **出典**: https://www.edrdg.org/enamdict/enamdict_doc.html
- **ライセンス**: Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
- **利用許諾**: https://www.edrdg.org/edrdg/licence.html
- **条文**: https://creativecommons.org/licenses/by-sa/4.0/legalcode
- **改変の有無**: **改変している。** 種別が 人物の姓名 (person)・地名 (place)・駅名 (station)・組織名 (organization)・会社名 (company) のエントリだけを採り、表記と読み (reb) を Roman の辞書形式へ変換した。姓・名の単独 (surname / given / fem / masc) と unclass は採っていない。抽出条件は開発用リポジトリの `server/tools/extract-names.py` に記録している
- **元データの版**: JMnedict 2026-08-19 生成版 (names-jmnedict.tsv の1行目に記録)
- **更新**: idiom.tsv と同じ手続き — **リリースビルド (release.sh) は、元データの生成日が90日より古いとビルドを中止する**。更新は JMnedict.xml.gz を再取得し extract-names.py を再実行する

## 医薬品の成分名リスト — 公共データ利用規約 (第1.0版) の出典表示

配布物内の `server/dict/katakana-drug.tsv` に適用される。 同規約は出典の記載と、加工した場合にその旨の記載を求めている(国が作成したかのように表示してはならない)。

- **出典**: 厚生労働省「薬価基準収載品目リスト」「処方箋に記載する一般名処方の標準的な記載(一般名処方マスタ)」
- **URL**: https://www.mhlw.go.jp/topics/2026/04/tp20260401-01.html ・ https://www.mhlw.go.jp/seisakunitsuite/bunya/kenkou_iryou/iryouhoken/shohosen_250401.html
- **利用条件**: 公共データ利用規約(第1.0版) https://www.mhlw.go.jp/chosakuken/index.html
- **加工の有無**: **加工している。** 成分名の列からカタカナ表記のものだけを抜き出し、読み(ひらがな)を機械導出して一覧にした。**本一覧は Roman が加工したものであり、厚生労働省が作成・公表したものではない**

## 上場会社名リスト — 公共データ利用規約 (第1.0版) の出典表示

配布物内の `server/dict/corp.tsv` に適用される。 同規約は出典の記載と、加工した場合にその旨の記載を求めている(国が作成したかのように表示してはならない)。

- **出典**: 金融庁 EDINET「EDINETコードリスト」(`EdinetcodeDlInfo.csv` / 2026-08-15 取得)
- **URL**: https://disclosure2dl.edinet-fsa.go.jp/guide/static/disclosure/WZEK0030.html
- **利用条件**: 公共データ利用規約(第1.0版)。EDINET の利用規約が同規約に準拠する旨を定めている
- **加工の有無**: **加工している。** 上場区分が「上場」の提出者だけを抜き出し、提出者名から「株式会社」等を、提出者名(ヨミ)から対応するヨミを除去したうえで、ヨミをひらがなへ機械変換して読みとし、変換の実測で必要と確認できた 884 社に絞って一覧にした。**本一覧は Roman が加工したものであり、金融庁が作成・公表したものではない**

## 辞書以外の同梱物 — 条文原文の所在

辞書データ以外の同梱コンポーネントについては、上流が配布する LICENSE ファイルを そのままの形で配布物に含めている。インストール先 (`~/Library/Application Support/Roman/`) からの相対位置は次のとおり。

| コンポーネント | ライセンス | 配布物内の条文 |
| --- | --- | --- |
| llama.cpp (llama-server) | MIT | `runtime/llama.cpp/LICENSE` |
| Node.js ランタイム | MIT 系(OpenSSL・ICU 等の表示を含む) | `runtime/node/LICENSE` |
| kuromoji.js | Apache-2.0 ＋ IPADIC | `server/node_modules/kuromoji/LICENSE-2.0.txt` ・ `NOTICE.md` |
| lodash / async / doublearray / zlibjs | MIT | `server/node_modules/<各パッケージ>/LICENSE` |
| zenz-v3-small (GGUF) | CC BY-SA 4.0 | 上流が LICENSE ファイルを配布していないため、下記の帰属表示をもって条件を満たす |

## zenz-v3-small — CC BY-SA 4.0 の帰属表示

配布物内の `runtime/zenz-v3-small.gguf` に適用される。 CC BY-SA 4.0 第3条(a)(1) が求める表示を以下に掲げる。同条(a)(1)(C) は 条文原文の同梱に代えて URI の提示を認めているため、条文は下記リンクで示す。

- **作品**: zenz-v3-small (GGUF)
- **作者**: Miwa Keita
- **出典**: https://huggingface.co/Miwa-Keita/zenz-v3-small-gguf
- **ライセンス**: Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
- **条文**: https://creativecommons.org/licenses/by-sa/4.0/legalcode
- **改変の有無**: **改変していない。** 上流の配布物をそのまま同梱している(ビルド時に sha256 で同一性を検証)

本ライセンスの share-alike 条項は改変物 (Adapted Material) に対してのみ働く。 Roman は上記のとおり無改変で同梱しているため、Roman 本体および他の同梱物に CC BY-SA 4.0 は及ばない。 なお [TERMS.md](../TERMS.md) 第3条の再配布・改変の禁止は、同第4条のとおり本モデルには適用されない。
