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
| `emoji.tsv` | 絵文字 — 収録と並び順は Unicode `emoji-test.txt` 由来、読みは mozc `emoji_data.tsv` 由来 | Unicode License v3(下記の帰属表示)＋ 上記 mozc 本体と同じ条文 |
| `org-names.tsv` | 組織名リスト(Wikidata 由来) | CC0 1.0(保持義務なし。下記参照) |
| `org-conv.tsv` | 店名・企業名の変換用辞書(上記 `org-names.tsv` から読みを機械導出した生成物) | 同上(CC0 1.0) |
| `katakana-conv.tsv` | 外来語の変換用辞書(上記 `katakana-mozc.tsv` のうち mozc 本体に無い語を写した生成物。語は UniDic 由来) | 上記 mozc 本体と同じ条文 ＋ 修正BSD(UniDic) |
| `med-disease.tsv` | 病名・症状(万病辞書 由来) | CC BY 4.0(下記の帰属表示) |
| `katakana-drug.tsv` | 医薬品の成分名(厚生労働省の公表資料 由来) | 公共データ利用規約(第1.0版)(下記の出典表示) |
| `corp.tsv` | 上場会社名(金融庁 EDINET の公表資料 由来) | 公共データ利用規約(第1.0版)(下記の出典表示) |
| `idiom.tsv` | 慣用句・ことわざ・四字熟語(JMdict 由来) | CC BY-SA 4.0(下記の帰属表示) |
| `names-jmnedict.tsv` | 固有名詞 — 人物の姓名・地名・駅名・組織名・会社名(JMnedict 由来) | CC BY-SA 4.0(下記の帰属表示) |
| `kanji.tsv` | 単漢字 — 常用漢字の音読み・訓読み(KANJIDIC2 由来) | CC BY-SA 4.0(下記の帰属表示) |
| `unidic.tsv` | UniDic から移植した語(選別に JMdict を使用) | 修正BSD(UniDic)+ CC BY-SA 4.0(下記の帰属表示) |
| `law-skk.tsv` | 法律用語(SKK-JISYO.law 由来) | GNU GPL v2 以降(下記の条文原文と帰属表示。**本ファイル自体は GPL で配布される**) |
| `katakana-it.tsv` / `extra.tsv` / `noun-types.tsv` / 各 `*-deny.tsv` | 本プロジェクトで新規作成した語彙・規則リスト | 本プロジェクトに帰属(第三者条文の適用なし) |

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

## 単漢字リスト — CC BY-SA 4.0 の帰属表示

配布物内の `server/dict/kanji.tsv` に適用される。 この抽出物は KANJIDIC2 の派生物であり、CC BY-SA 4.0 の share-alike 条項により**本ファイル自体も CC BY-SA 4.0 で配布される** (idiom.tsv・names-jmnedict.tsv と同じ扱い。[TERMS.md](../TERMS.md) 第3条の再配布・改変の禁止は第4条のとおり本ファイルには適用されない)。share-alike が及ぶのは本ファイルまでで、Roman 本体および他の同梱物には及ばない。

- **作品**: KANJIDIC2 (Kanji Information in XML)
- **著作権者**: Electronic Dictionary Research and Development Group (EDRDG) / James William Breen
- **出典**: https://www.edrdg.org/kanjidic/kanjd2index.html
- **ライセンス**: Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
- **利用許諾**: https://www.edrdg.org/edrdg/licence.html
- **条文**: https://creativecommons.org/licenses/by-sa/4.0/legalcode
- **改変の有無**: **改変している。** 常用漢字 (grade 1-6 の教育漢字と grade 8 の中学以降。2,136字) だけを採り、音読み (ja_on) はひらがなに直し、訓読みは送り仮名の無いもの (峠=とうげ) だけを採って、Roman の辞書形式へ変換した。送り仮名を伴う訓 (突=つ.く)・接頭接尾の印が付く読み・人名用漢字 (grade 9-10)・表外字は採っていない。mozc が同じ読みで同じ単漢字を既に持つ組も入れていない。抽出条件は開発用リポジトリの `server/tools/extract-kanji.py` に記録している
- **元データの版**: KANJIDIC2 2026-235 (生成日 2026-08-23。kanji.tsv の1行目に記録)
- **更新**: idiom.tsv と同じ手続き — **リリースビルド (release.sh) は、元データの生成日が90日より古いとビルドを中止する**。更新は kanjidic2.xml.gz を再取得し extract-kanji.py を再実行する

## UniDic 移植辞書 — 修正BSD と CC BY-SA 4.0 の帰属表示

配布物内の `server/dict/unidic.tsv` に適用される。 このファイルは**2つの資料に由来する**: 語 (読みと表記) は UniDic から採り、そのうちどれを残すかの選別に JMdict を使っている。選別が JMdict の収録判断に依っているため、**本ファイルは安全側に倒して CC BY-SA 4.0 で配布する** (idiom.tsv と同じ扱い。[TERMS.md](../TERMS.md) 第3条の再配布・改変の禁止は第4条のとおり本ファイルには適用されない)。share-alike が及ぶのは本ファイルまでで、Roman 本体および他の同梱物には及ばない。

**語の出所 (修正BSD)**

- **作品**: UniDic (現代書き言葉 UniDic / `unidic-cwj-202512`)
- **著作権者**: 大学共同利用機関法人 人間文化研究機構 国立国語研究所 (NINJAL)
- **出典**: https://clrd.ninjal.ac.jp/unidic/
- **ライセンス**: 修正BSD (UniDic は GPL v2 / LGPL v2.1 / 修正BSD の三択で提供されており、Roman は修正BSD を選択する)
- **改変の有無**: **改変している。** 語彙表 `lex.csv` から体言・形状詞・副詞の 読み+表記 を採り、下記の条件で絞り込んで Roman の辞書形式へ変換した。抽出条件は開発用リポジトリの `server/tools/extract-unidic.py` に記録している
- **元データの版**: `unidic-cwj-202512` (unidic.tsv の1行目に記録)

**選別に使った資料 (CC BY-SA 4.0)**

- **作品**: JMdict (Japanese-Multilingual Dictionary)
- **著作権者**: Electronic Dictionary Research and Development Group (EDRDG) / James William Breen
- **出典**: http://www.edrdg.org/jmdict/j_jmdict.html
- **ライセンス**: Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
- **利用許諾**: https://www.edrdg.org/edrdg/licence.html
- **条文**: https://creativecommons.org/licenses/by-sa/4.0/legalcode
- **使い方**: JMdict に現代の表記として載る語だけを残すための照合に使っている (稀用表記 rK・旧字 oK・誤用 iK・検索専用 sK の表記、古語 arch・廃語 obs だけの語義は除外)。JMdict の語義・訳語は含まない
- **更新**: idiom.tsv と同じ手続き — **リリースビルド (release.sh) は、元データの生成日が90日より古いとビルドを中止する**。更新は lex.csv と JMdict_e.gz を再取得し extract-unidic.py を再実行する

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

## 法律用語辞書 — GNU General Public License v2 以降

配布物内の `server/dict/law-skk.tsv` に適用される。 このファイルは SKK の法律用語辞書 SKK-JISYO.law の派生物であり、GPL の条項により**本ファイル自体は GPL-2.0-or-later で配布される** (idiom.tsv・names-jmnedict.tsv と同じ扱い。[TERMS.md](../TERMS.md) 第3条の再配布・改変の禁止は第4条のとおり本ファイルには適用されない)。GPL の効力が及ぶのは本ファイルまでで、Roman 本体および他の同梱物には及ばない。本ファイルは実行時に変換サーバが読み込むデータであり、Roman 本体とリンクされるものではない (単純な集積配布)。本ファイルの「ソースコード」は本ファイル自体 (プレーンテキストの TSV) である。

- **作品**: SKK-JISYO.law (法律用語辞書 for SKK system)
- **著作権者**: Copyright (C) 1998-1999 小松 弘 (Hiroshi Komatsu) / Copyright (C) 2001, 2003, 2004 Mikio NAKAJIMA / SKK Development Team
- **原著作**: 小松弘弁護士「法律用語電子化辞書 LKKS」
- **出典**: https://github.com/skk-dev/dict/blob/master/SKK-JISYO.law (コミット f415e667 / 2019-04-27。sha256 `11c674dfc8b106d12ba216e07fb8762e7d89df15a81fa79cc8e48984a6af03be`)
- **ライセンス**: GNU General Public License, version 2 or (at your option) any later version
- **条文**: 下記に全文を掲げる (https://www.gnu.org/licenses/old-licenses/gpl-2.0.txt)
- **改変の有無**: **改変している (GPL v2 第2条(a) の表示)。改変日 2026-09-05。** 元データ 12,409 組 (読みと表記) のうち、Roman の変換で部品の合成に失敗し、1 語として足せば正しくなるもの 3,404 組だけを機械的に選別し、品詞 (名詞) とコスト (7500) を付けて Roman の辞書形式へ変換した。選別の規則 (読み 3 字以下・送り仮名の違いだけの語・辞書の 1 語を押しのける語・旧字を含む語などの除外) は開発用リポジトリの `server/tools/gen-law-skk.js` に記録している
- **元データの版**: 上流の最終更新は 2019-04-27 (原著作は 1998-99 年)。上流に更新が無いため、更新の手続きは設けない

```
                    GNU GENERAL PUBLIC LICENSE
                       Version 2, June 1991

 Copyright (C) 1989, 1991 Free Software Foundation, Inc.,
 <https://fsf.org/>
 Everyone is permitted to copy and distribute verbatim copies
 of this license document, but changing it is not allowed.

                            Preamble

  The licenses for most software are designed to take away your
freedom to share and change it.  By contrast, the GNU General Public
License is intended to guarantee your freedom to share and change free
software--to make sure the software is free for all its users.  This
General Public License applies to most of the Free Software
Foundation's software and to any other program whose authors commit to
using it.  (Some other Free Software Foundation software is covered by
the GNU Lesser General Public License instead.)  You can apply it to
your programs, too.

  When we speak of free software, we are referring to freedom, not
price.  Our General Public Licenses are designed to make sure that you
have the freedom to distribute copies of free software (and charge for
this service if you wish), that you receive source code or can get it
if you want it, that you can change the software or use pieces of it
in new free programs; and that you know you can do these things.

  To protect your rights, we need to make restrictions that forbid
anyone to deny you these rights or to ask you to surrender the rights.
These restrictions translate to certain responsibilities for you if you
distribute copies of the software, or if you modify it.

  For example, if you distribute copies of such a program, whether
gratis or for a fee, you must give the recipients all the rights that
you have.  You must make sure that they, too, receive or can get the
source code.  And you must show them these terms so they know their
rights.

  We protect your rights with two steps: (1) copyright the software, and
(2) offer you this license which gives you legal permission to copy,
distribute and/or modify the software.

  Also, for each author's protection and ours, we want to make certain
that everyone understands that there is no warranty for this free
software.  If the software is modified by someone else and passed on, we
want its recipients to know that what they have is not the original, so
that any problems introduced by others will not reflect on the original
authors' reputations.

  Finally, any free program is threatened constantly by software
patents.  We wish to avoid the danger that redistributors of a free
program will individually obtain patent licenses, in effect making the
program proprietary.  To prevent this, we have made it clear that any
patent must be licensed for everyone's free use or not licensed at all.

  The precise terms and conditions for copying, distribution and
modification follow.

                    GNU GENERAL PUBLIC LICENSE
   TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

  0. This License applies to any program or other work which contains
a notice placed by the copyright holder saying it may be distributed
under the terms of this General Public License.  The "Program", below,
refers to any such program or work, and a "work based on the Program"
means either the Program or any derivative work under copyright law:
that is to say, a work containing the Program or a portion of it,
either verbatim or with modifications and/or translated into another
language.  (Hereinafter, translation is included without limitation in
the term "modification".)  Each licensee is addressed as "you".

Activities other than copying, distribution and modification are not
covered by this License; they are outside its scope.  The act of
running the Program is not restricted, and the output from the Program
is covered only if its contents constitute a work based on the
Program (independent of having been made by running the Program).
Whether that is true depends on what the Program does.

  1. You may copy and distribute verbatim copies of the Program's
source code as you receive it, in any medium, provided that you
conspicuously and appropriately publish on each copy an appropriate
copyright notice and disclaimer of warranty; keep intact all the
notices that refer to this License and to the absence of any warranty;
and give any other recipients of the Program a copy of this License
along with the Program.

You may charge a fee for the physical act of transferring a copy, and
you may at your option offer warranty protection in exchange for a fee.

  2. You may modify your copy or copies of the Program or any portion
of it, thus forming a work based on the Program, and copy and
distribute such modifications or work under the terms of Section 1
above, provided that you also meet all of these conditions:

    a) You must cause the modified files to carry prominent notices
    stating that you changed the files and the date of any change.

    b) You must cause any work that you distribute or publish, that in
    whole or in part contains or is derived from the Program or any
    part thereof, to be licensed as a whole at no charge to all third
    parties under the terms of this License.

    c) If the modified program normally reads commands interactively
    when run, you must cause it, when started running for such
    interactive use in the most ordinary way, to print or display an
    announcement including an appropriate copyright notice and a
    notice that there is no warranty (or else, saying that you provide
    a warranty) and that users may redistribute the program under
    these conditions, and telling the user how to view a copy of this
    License.  (Exception: if the Program itself is interactive but
    does not normally print such an announcement, your work based on
    the Program is not required to print an announcement.)

These requirements apply to the modified work as a whole.  If
identifiable sections of that work are not derived from the Program,
and can be reasonably considered independent and separate works in
themselves, then this License, and its terms, do not apply to those
sections when you distribute them as separate works.  But when you
distribute the same sections as part of a whole which is a work based
on the Program, the distribution of the whole must be on the terms of
this License, whose permissions for other licensees extend to the
entire whole, and thus to each and every part regardless of who wrote it.

Thus, it is not the intent of this section to claim rights or contest
your rights to work written entirely by you; rather, the intent is to
exercise the right to control the distribution of derivative or
collective works based on the Program.

In addition, mere aggregation of another work not based on the Program
with the Program (or with a work based on the Program) on a volume of
a storage or distribution medium does not bring the other work under
the scope of this License.

  3. You may copy and distribute the Program (or a work based on it,
under Section 2) in object code or executable form under the terms of
Sections 1 and 2 above provided that you also do one of the following:

    a) Accompany it with the complete corresponding machine-readable
    source code, which must be distributed under the terms of Sections
    1 and 2 above on a medium customarily used for software interchange; or,

    b) Accompany it with a written offer, valid for at least three
    years, to give any third party, for a charge no more than your
    cost of physically performing source distribution, a complete
    machine-readable copy of the corresponding source code, to be
    distributed under the terms of Sections 1 and 2 above on a medium
    customarily used for software interchange; or,

    c) Accompany it with the information you received as to the offer
    to distribute corresponding source code.  (This alternative is
    allowed only for noncommercial distribution and only if you
    received the program in object code or executable form with such
    an offer, in accord with Subsection b above.)

The source code for a work means the preferred form of the work for
making modifications to it.  For an executable work, complete source
code means all the source code for all modules it contains, plus any
associated interface definition files, plus the scripts used to
control compilation and installation of the executable.  However, as a
special exception, the source code distributed need not include
anything that is normally distributed (in either source or binary
form) with the major components (compiler, kernel, and so on) of the
operating system on which the executable runs, unless that component
itself accompanies the executable.

If distribution of executable or object code is made by offering
access to copy from a designated place, then offering equivalent
access to copy the source code from the same place counts as
distribution of the source code, even though third parties are not
compelled to copy the source along with the object code.

  4. You may not copy, modify, sublicense, or distribute the Program
except as expressly provided under this License.  Any attempt
otherwise to copy, modify, sublicense or distribute the Program is
void, and will automatically terminate your rights under this License.
However, parties who have received copies, or rights, from you under
this License will not have their licenses terminated so long as such
parties remain in full compliance.

  5. You are not required to accept this License, since you have not
signed it.  However, nothing else grants you permission to modify or
distribute the Program or its derivative works.  These actions are
prohibited by law if you do not accept this License.  Therefore, by
modifying or distributing the Program (or any work based on the
Program), you indicate your acceptance of this License to do so, and
all its terms and conditions for copying, distributing or modifying
the Program or works based on it.

  6. Each time you redistribute the Program (or any work based on the
Program), the recipient automatically receives a license from the
original licensor to copy, distribute or modify the Program subject to
these terms and conditions.  You may not impose any further
restrictions on the recipients' exercise of the rights granted herein.
You are not responsible for enforcing compliance by third parties to
this License.

  7. If, as a consequence of a court judgment or allegation of patent
infringement or for any other reason (not limited to patent issues),
conditions are imposed on you (whether by court order, agreement or
otherwise) that contradict the conditions of this License, they do not
excuse you from the conditions of this License.  If you cannot
distribute so as to satisfy simultaneously your obligations under this
License and any other pertinent obligations, then as a consequence you
may not distribute the Program at all.  For example, if a patent
license would not permit royalty-free redistribution of the Program by
all those who receive copies directly or indirectly through you, then
the only way you could satisfy both it and this License would be to
refrain entirely from distribution of the Program.

If any portion of this section is held invalid or unenforceable under
any particular circumstance, the balance of the section is intended to
apply and the section as a whole is intended to apply in other
circumstances.

It is not the purpose of this section to induce you to infringe any
patents or other property right claims or to contest validity of any
such claims; this section has the sole purpose of protecting the
integrity of the free software distribution system, which is
implemented by public license practices.  Many people have made
generous contributions to the wide range of software distributed
through that system in reliance on consistent application of that
system; it is up to the author/donor to decide if he or she is willing
to distribute software through any other system and a licensee cannot
impose that choice.

This section is intended to make thoroughly clear what is believed to
be a consequence of the rest of this License.

  8. If the distribution and/or use of the Program is restricted in
certain countries either by patents or by copyrighted interfaces, the
original copyright holder who places the Program under this License
may add an explicit geographical distribution limitation excluding
those countries, so that distribution is permitted only in or among
countries not thus excluded.  In such case, this License incorporates
the limitation as if written in the body of this License.

  9. The Free Software Foundation may publish revised and/or new versions
of the General Public License from time to time.  Such new versions will
be similar in spirit to the present version, but may differ in detail to
address new problems or concerns.

Each version is given a distinguishing version number.  If the Program
specifies a version number of this License which applies to it and "any
later version", you have the option of following the terms and conditions
either of that version or of any later version published by the Free
Software Foundation.  If the Program does not specify a version number of
this License, you may choose any version ever published by the Free Software
Foundation.

  10. If you wish to incorporate parts of the Program into other free
programs whose distribution conditions are different, write to the author
to ask for permission.  For software which is copyrighted by the Free
Software Foundation, write to the Free Software Foundation; we sometimes
make exceptions for this.  Our decision will be guided by the two goals
of preserving the free status of all derivatives of our free software and
of promoting the sharing and reuse of software generally.

                            NO WARRANTY

  11. BECAUSE THE PROGRAM IS LICENSED FREE OF CHARGE, THERE IS NO WARRANTY
FOR THE PROGRAM, TO THE EXTENT PERMITTED BY APPLICABLE LAW.  EXCEPT WHEN
OTHERWISE STATED IN WRITING THE COPYRIGHT HOLDERS AND/OR OTHER PARTIES
PROVIDE THE PROGRAM "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED
OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE.  THE ENTIRE RISK AS
TO THE QUALITY AND PERFORMANCE OF THE PROGRAM IS WITH YOU.  SHOULD THE
PROGRAM PROVE DEFECTIVE, YOU ASSUME THE COST OF ALL NECESSARY SERVICING,
REPAIR OR CORRECTION.

  12. IN NO EVENT UNLESS REQUIRED BY APPLICABLE LAW OR AGREED TO IN WRITING
WILL ANY COPYRIGHT HOLDER, OR ANY OTHER PARTY WHO MAY MODIFY AND/OR
REDISTRIBUTE THE PROGRAM AS PERMITTED ABOVE, BE LIABLE TO YOU FOR DAMAGES,
INCLUDING ANY GENERAL, SPECIAL, INCIDENTAL OR CONSEQUENTIAL DAMAGES ARISING
OUT OF THE USE OR INABILITY TO USE THE PROGRAM (INCLUDING BUT NOT LIMITED
TO LOSS OF DATA OR DATA BEING RENDERED INACCURATE OR LOSSES SUSTAINED BY
YOU OR THIRD PARTIES OR A FAILURE OF THE PROGRAM TO OPERATE WITH ANY OTHER
PROGRAMS), EVEN IF SUCH HOLDER OR OTHER PARTY HAS BEEN ADVISED OF THE
POSSIBILITY OF SUCH DAMAGES.

                     END OF TERMS AND CONDITIONS

            How to Apply These Terms to Your New Programs

  If you develop a new program, and you want it to be of the greatest
possible use to the public, the best way to achieve this is to make it
free software which everyone can redistribute and change under these terms.

  To do so, attach the following notices to the program.  It is safest
to attach them to the start of each source file to most effectively
convey the exclusion of warranty; and each file should have at least
the "copyright" line and a pointer to where the full notice is found.

    <one line to give the program's name and a brief idea of what it does.>
    Copyright (C) <year>  <name of author>

    This program is free software; you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation; either version 2 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License along
    with this program; if not, see <https://www.gnu.org/licenses/>.

Also add information on how to contact you by electronic and paper mail.

If the program is interactive, make it output a short notice like this
when it starts in an interactive mode:

    Gnomovision version 69, Copyright (C) year name of author
    Gnomovision comes with ABSOLUTELY NO WARRANTY; for details type `show w'.
    This is free software, and you are welcome to redistribute it
    under certain conditions; type `show c' for details.

The hypothetical commands `show w' and `show c' should show the appropriate
parts of the General Public License.  Of course, the commands you use may
be called something other than `show w' and `show c'; they could even be
mouse-clicks or menu items--whatever suits your program.

You should also get your employer (if you work as a programmer) or your
school, if any, to sign a "copyright disclaimer" for the program, if
necessary.  Here is a sample; alter the names:

  Yoyodyne, Inc., hereby disclaims all copyright interest in the program
  `Gnomovision' (which makes passes at compilers) written by James Hacker.

  <signature of Moe Ghoul>, 1 April 1989
  Moe Ghoul, President of Vice

This General Public License does not permit incorporating your program into
proprietary programs.  If your program is a subroutine library, you may
consider it more useful to permit linking proprietary applications with the
library.  If this is what you want to do, use the GNU Lesser General
Public License instead of this License.
```

## 辞書以外の同梱物 — 条文原文の所在

辞書データ以外の同梱コンポーネントについては、上流が配布する LICENSE ファイルを そのままの形で配布物に含めている。インストール先 (`~/Library/Application Support/Roman/`) からの相対位置は次のとおり。

| コンポーネント | ライセンス | 配布物内の条文 |
| --- | --- | --- |
| llama.cpp (llama-server) | MIT | `runtime/llama.cpp/LICENSE` |
| Node.js ランタイム | MIT 系(OpenSSL・ICU 等の表示を含む) | `runtime/node/LICENSE` |
| kuromoji.js | Apache-2.0 ＋ IPADIC | `server/node_modules/kuromoji/LICENSE-2.0.txt` ・ `NOTICE.md` |
| lodash / async / doublearray / zlibjs | MIT | `server/node_modules/<各パッケージ>/LICENSE` |
| zenz-v3-small (GGUF) | CC BY-SA 4.0 | 上流が LICENSE ファイルを配布していないため、下記の帰属表示をもって条件を満たす |

## Unicode 絵文字データ — Unicode License v3 の帰属表示

配布物内の `server/dict/emoji.tsv` のうち、**どの文字を収録するかと並び順**が Unicode の資料に由来する (読みの部分は mozc 由来で、上記 mozc 本体の条文が適用される)。

- **作品**: Unicode® Emoji Keyboard/Display Test Data (`emoji-test.txt`) — Emoji Version 17.0 (2025-08-04)
- **著作権表示**: © 2025 Unicode®, Inc.
- **出典**: https://unicode.org/Public/emoji/latest/emoji-test.txt
- **利用条件**: https://www.unicode.org/terms_of_use.html
- **ライセンス条文**: https://www.unicode.org/license.txt (Unicode License v3)
- **商標**: Unicode および Unicode ロゴは、米国その他の国における Unicode, Inc. の登録商標である
- **改変の有無**: **改変している。** 原ファイルから完全修飾形の絵文字と並び順だけを取り出し、mozc 由来の読みと突き合わせて `emoji.tsv` を生成した。肌の色の変種は収録していない。原ファイルは同梱しない

## zenz-v3-small — CC BY-SA 4.0 の帰属表示

配布物内の `runtime/zenz-v3-small.gguf` に適用される。 CC BY-SA 4.0 第3条(a)(1) が求める表示を以下に掲げる。同条(a)(1)(C) は 条文原文の同梱に代えて URI の提示を認めているため、条文は下記リンクで示す。

- **作品**: zenz-v3-small (GGUF)
- **作者**: Miwa Keita
- **出典**: https://huggingface.co/Miwa-Keita/zenz-v3-small-gguf
- **ライセンス**: Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
- **条文**: https://creativecommons.org/licenses/by-sa/4.0/legalcode
- **改変の有無**: **改変していない。** 上流の配布物をそのまま同梱している(ビルド時に sha256 で同一性を検証)

本ライセンスの share-alike 条項は改変物 (Adapted Material) に対してのみ働く。 Roman は上記のとおり無改変で同梱しているため、Roman 本体および他の同梱物に CC BY-SA 4.0 は及ばない。 なお [TERMS.md](../TERMS.md) 第3条の再配布・改変の禁止は、同第4条のとおり本モデルには適用されない。
