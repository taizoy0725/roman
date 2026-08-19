# Roman のライセンス

Roman が使用する全コンポーネントの出自・ライセンスと、義務の履行状況の記録。 コンポーネントは **配布物 (.pkg) に同梱するもの** と **同梱せず利用者のマシン上の別ソフトとして使うもの** に分かれ、 再配布に伴う義務が生じるのは前者だけである。

最終確認: 2026-08-15(v1.07 の配布物 — `native/ime/release.sh` が生成する pkg を展開した実同梱物 — に基づく。同梱物の版・ライセンス文書の実在をすべて実物で照合した。Llama-3-ELYZA-JP-8B は削除済みで、同梱するモデルは zenz-v3-small のみ)。

## 同梱するコンポーネント

.pkg に含まれ、インストール時に IME 本体は `/Library/Input Methods/Roman.app` へ、 それ以外は `~/Library/Application Support/Roman/` 配下へ置かれる。 下記の義務はすべてこの配布物に対して生じる。

| コンポーネント | 版 | 役割 | 配布物内の位置 | ライセンス | 義務と履行状況 |
| --- | --- | --- | --- | --- | --- |
| Roman 本体(入力メソッド・変換サーバ・辞書構築物) | 1.07 | — | `Roman.app` / `server/` | 作者が定める利用条件(All rights reserved) | 利用条件は [TERMS.md](../TERMS.md) |
| zenz-v3-small (GGUF) | — | かな漢字変換モデル (95M / 72MB)。辞書ラティスが実変換を出せない読み(新語など)を担う | `runtime/zenz-v3-small.gguf` | CC BY-SA 4.0 | 作者表示 (Miwa Keita) → 帰属表示を `docs/NOTICE.md` に同梱。**本一覧で最も注意が必要** — 詳細は下記の専用節 |
| llama.cpp (llama-server と共有ライブラリ) | b9960 | zenz と Qwen の推論ランタイム | `runtime/llama.cpp/` | MIT | 著作権表示とライセンス文の保持 → 上流の原文を `runtime/llama.cpp/LICENSE` としてそのまま同梱 |
| Node.js ランタイム | v22.23.2 | 変換サーバの実行系 | `runtime/node/node` | MIT 系(同梱依存の個別表示を含む) | 公式配布物の LICENSE 全文(OpenSSL・ICU 等の表示を含む)を `runtime/node/LICENSE` としてそのまま同梱 |
| CPython (python-build-standalone) | 3.12.13 | BERT の実行系。初回起動時にこの Python で venv を作り、PyTorch 等を導入する | `runtime/python/` | PSF License (CPython 本体) | 条文の保持 → 上流ビルドに含まれる `lib/python3.12/LICENSE.txt` (PSF 条文と同梱依存の表示) をそのまま同梱。署名に `disable-library-validation` を付与 (torch の dylib が別 Team ID のため) |
| kuromoji.js | 0.1.2 | 読み検証・形態素解析 | `server/node_modules/kuromoji/` | Apache-2.0(同梱辞書 mecab-ipadic-2.7.0 は IPADIC 条項) | 上流パッケージの `LICENSE-2.0.txt` と `NOTICE.md` (IPADIC) を含めたまま同梱 |
| lodash 4.18.1 / async 2.6.4 / doublearray 0.0.2 / zlibjs 0.3.1 | — | kuromoji.js の依存 | `server/node_modules/` | MIT | 各パッケージの LICENSE ファイルを含めたまま同梱 |
| 変換辞書(mozc OSS 辞書由来ほか) | — | ラティス変換の辞書・接続コスト | `server/dict/` | BSD-3-Clause / IPAdic (NAIST) / ICOT / Public Domain / CC0 | 条文原文の保持 → [NOTICE.md](NOTICE.md) に全文を掲載し、同ファイルを `docs/NOTICE.md` として同梱 |
| 病名・症状リスト(万病辞書 由来) | MANBYO_202106 | 病名・症状の変換 | `server/dict/med-disease.tsv` | CC BY 4.0 | 作者表示と改変の明示 → [NOTICE.md](NOTICE.md) に帰属表示を掲載。share-alike 条項は無く、他の同梱物に波及しない |
| 医薬品の成分名リスト(厚生労働省の公表資料 由来) | 2026-08-01 適用版ほか | 医薬品名の変換 | `server/dict/katakana-drug.tsv` | 公共データ利用規約(第1.0版) | 出典の記載と加工の明示 → [NOTICE.md](NOTICE.md) に記載 |
| 慣用句・ことわざリスト(JMdict 由来) | 2026-08-12 取得版 | 慣用句・ことわざ・四字熟語の変換 | `server/dict/idiom.tsv` | CC BY-SA 4.0 | 帰属表示と share-alike → [NOTICE.md](NOTICE.md) に帰属表示。share-alike は本ファイル自体に適用され (CC BY-SA のまま配布)、他の同梱物へは及ばない |
| 固有名詞リスト(JMnedict 由来) | 2026-08-19 取得版 | 人物の姓名・地名・駅名・組織名・会社名の変換 | `server/dict/names-jmnedict.tsv` | CC BY-SA 4.0 | 帰属表示と share-alike → [NOTICE.md](NOTICE.md) に帰属表示。share-alike は本ファイル自体に適用され (CC BY-SA のまま配布)、他の同梱物へは及ばない |

## 同梱しないコンポーネント(利用者のマシン上の別ソフト)

**配布物には一切含めず**、初回起動時に利用者の許諾を得て、それぞれの公式配布元から利用者のマシンへ取得するもの。 Roman が再配布するわけではないため、**再配布に伴う義務は生じない**(取得先の各ライセンスが利用者に直接適用される)。 何に依存しているかの記録として残す。

| コンポーネント | 役割 | 出自 | ライセンス |
| --- | --- | --- | --- |
| Qwen3.5-4B (GGUF・4ビット量子化) | 候補の裁定 LLM(僅差の文節解を全文で選び直す)。同梱の llama-server で動かす | 元モデル [Qwen/Qwen3.5-4B](https://huggingface.co/Qwen/Qwen3.5-4B)。GGUF 化と4ビット量子化は本プロジェクトで実施し、[Release](https://github.com/taizoy0725/roman/releases/tag/models-qwen3.5-4b) から配布(2分割) | Apache 2.0(**改変あり**: llama.cpp による GGUF 変換と q4_k_m 量子化。変換器は llama.cpp 01818e4 / 2026-08-17) |
| bert-base-japanese-v3 | 候補の自然さ採点 (PLL) | [tohoku-nlp/bert-base-japanese-v3](https://huggingface.co/tohoku-nlp/bert-base-japanese-v3) | Apache 2.0 |
| PyTorch / Transformers / fugashi / unidic-lite | BERT の推論ランタイム。同梱 Python で作る venv (`state/bert-venv`) へ導入する | PyPI | BSD-3 / Apache 2.0 / BSD ほか |
| ollama (任意) | 既に導入済みの場合はそちらを尊重して使う。Roman が入れることはない | [ollama/ollama](https://github.com/ollama/ollama) | MIT |
| Apple Intelligence (FoundationModels) | 裁定バックエンドの実験系。既定 (`ARBITER_BACKEND=qwen`) では使わない | macOS 26 以降 | Apple SLA |
| Swift / macOS SDK | ビルド基盤 | — | Apple SLA |

実験系の `apple-arbiter-server`(ローカルビルドの Mach-O)は、公証が通らないため 配布物から明示的に除外している。

## zenz-v3-small — CC BY-SA 4.0

- 帰属表示: 「zenz-v3-small © Miwa Keita — Creative Commons Attribution-ShareAlike 4.0 International」
- 条文: https://creativecommons.org/licenses/by-sa/4.0/legalcode
- 出典: https://huggingface.co/Miwa-Keita/zenz-v3-small-gguf (モデルカードの `license` は `cc-by-sa-4.0`。2026-08-11 に実物で確認)
- 履行状況: 上流の重みを**無改変のまま**同梱している(ビルド時に sha256 `501f605d…2083` で同一性を検証)。 したがって必要なのは帰属表示とライセンスへのリンクだけで、share-alike による派生モデル公開の義務は発生しない。 帰属表示は配布物内の `docs/NOTICE.md` に掲げる(第3条(a)(1) は表示を**配布物と共に**届けることを求めるため、 公開リポジトリでの表示だけでは足りない)
- 注意: 上流が供給している作者表示は **Miwa-Keita のみ**である。モデルカードに azooKey プロジェクトの表示はないため、 帰属表示に azooKey を含めない
- モデルを**改変**(追加学習・量子化変更等)して配布する場合は、派生モデルも CC BY-SA 4.0 で公開する義務(share-alike)が生じる
- share-alike の効力はモデル自体に限られ、Roman 本体のライセンスには及ばない(単純な集積配布)

## llama.cpp — MIT

- 条文: https://github.com/ggml-org/llama.cpp/blob/master/LICENSE
- 条件: 著作権表示とライセンス文を配布物に保持
- 履行状況: 公式リリース `b9960` の macOS/arm64 バイナリを sha256 検証のうえ取得し、 `llama-server` と必要な共有ライブラリ、および同アーカイブの `LICENSE` を同梱。 Homebrew 版を使わないのは、その成果物が ggml と openssl を `/opt/homebrew` の 絶対パスで参照しており配布先で解決できないため

## Node.js — MIT 系

- 条文: https://github.com/nodejs/node/blob/main/LICENSE
- 条件: Node.js の LICENSE ファイルは同梱依存 (OpenSSL, ICU 等) の表示を含むため、 ランタイムを同梱する場合は配布物の LICENSE をそのまま同梱する
- 履行状況: 公式 tarball `v22.23.2` (darwin-arm64) を sha256 検証のうえ取得し、 `node` 実行ファイルと同アーカイブの `LICENSE` を同梱。 配布物の公証要件に合わせて Developer ID で再署名しているが、ライセンス上の扱いは変わらない

## kuromoji.js — Apache-2.0 + IPADIC

- 条文: https://www.apache.org/licenses/LICENSE-2.0
- 条件: ライセンス文と上流 NOTICE の保持。kuromoji が同梱する辞書 mecab-ipadic-2.7.0 には IPADIC 条項(著作権表示の保持で再配布可)が適用される
- 履行状況: `node_modules` をそのまま同梱しているため、上流の `LICENSE-2.0.txt` と `NOTICE.md` が配布物に含まれている。 IPADIC の条文は [NOTICE.md](NOTICE.md) にも同一のものを掲載している (mozc 由来の辞書エントリと出自が同じため)

## 参考にした設計(コードのコピーはなし)

- azooKey / AzooKeyKanaKanjiConverter(MIT)— Zenzai方式(小型専用モデル＋投機的デコード)の設計思想を参考
- karukan(MIT OR Apache-2.0)— 辞書＋ニューラルのハイブリッド構成を参考
- 設計思想・アイデアの参照は著作権の対象外。プロンプト・FST・ガードレール等のコードはすべて本プロジェクトの書き下ろし

## 自作部分

入力メソッド本体・変換サーバ・辞書構築ツール、および本ドキュメント群は本プロジェクトのオリジナルです。 **著作権は作者に帰属します (All rights reserved)。** 無償で使えますが、ソースコードは公開しておらず、再配布・改変はできません。 詳しい利用条件は [TERMS.md](../TERMS.md) を参照してください。 上表の第三者コンポーネントについては、本項ではなくそれぞれの提供元が定めるライセンスが適用されます。

## 実務上の整理

- **配布物 (.pkg) について**: コピーレフトが Roman 本体のコードへ及ぶものは無い。 zenz の CC BY-SA は**モデルの重みにのみ**作用し、無改変で同梱している限り 必要なのは帰属表示だけ。他は MIT / Apache-2.0 / IPADIC / BSD-3 / PD / CC0 で、 いずれも「表示と条文の保持」で足りる。商用・非商用いずれも可
- **利用者環境へ取得するもの (Qwen・BERT・PyTorch) について**: Roman が再配布するわけではないため義務は生じない(取得は利用者の許諾のうえ公式配布元から行う)。 将来これらを pkg に同梱する設計へ変えた場合は、 それぞれの LICENSE / NOTICE の同梱が新たに必要になる
- **アップデート時に見直す箇所**: llama.cpp のビルド番号・Node.js / CPython のバージョンを 上げたときは、`release.sh` の sha256 と併せて本ページの版表記も更新する

## 履行状況のチェックリスト

- [x] 推論ランタイムの整理 — zenz と裁定用の Qwen は、どちらも同梱の llama-server で動かす (2026-08-12 第2段。ollama への依存を解消)
- [x] Qwen (2.8GB) は同梱せず、初回起動時に利用者の許諾を得て本プロジェクトの Release から取得する — GitHub Release の 1ファイル 2GiB 上限と、macOS 15 の pkg スクリプト 600 秒タイムアウトのため (2026-08-12)
- [x] BERT の実行環境 — Python (python-build-standalone) を同梱し、初回起動時に venv を構築する。同梱 Python の署名には `disable-library-validation` が必須 (torch の dylib は別 Team ID / 2026-08-12 第3段)
- [x] 同梱する各版の LICENSE 原文を .pkg に収録 — llama.cpp / Node.js / node_modules 各パッケージ / 辞書データの [NOTICE.md](NOTICE.md)
- [x] zenz の帰属表示を配布物内に置く — [NOTICE.md](NOTICE.md) に専用節を設け、`docs/NOTICE.md` として同梱する。 公開リポジトリの README.md からの参照だけでは第3条(a)(1) を満たさないため (2026-08-11)
- [x] 本ページ (LICENSES.md) と [TERMS.md](../TERMS.md) も .pkg に同梱する — 配置は publish/ の階層をそのまま写し、 NOTICE.md と LICENSES.md を `docs/` へ、TERMS.md をインストール先直下へ置く。 3ファイルが相互に張る相対リンクが配布物側でもそのまま解決する。 TERMS.md 第4条が「同梱の LICENSES.md」を参照しているため、実物が無いと記載と食い違う (2026-08-11)
- [x] ライセンス文書の同梱失敗を握り潰さない — `release.sh` は3件の存在を検査し、欠けていればビルドを止める。 従来は `2>/dev/null || true` で、欠けたまま .pkg ができる状態だった (2026-08-11)

### v1.0 初回出荷分 (2026-08-10) の未履行 — 解消済み

2026-08-10 に生成した最初の `Roman-1.0.pkg` は Markdown 化前の版で、`runtime/NOTICE.html` に **zenz の帰属表示を含んでいなかった**(導入済み環境の実物で確認済み)。 CC BY-SA 4.0 第3条(a)(1) を満たしていなかったが、**2026-08-12 に差し替えた配布物で解消済み**(pkg を展開し `docs/NOTICE.md` の同梱を実物で確認)。
