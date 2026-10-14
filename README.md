# iPhoneでGTA Vをプレイ（5★ Port）

> [!TIP]
> **🆕 v1.2の新機能：パソコンなしで、iPhoneから直接アプリをビルドできます。**
> **[fivestarport.vercel.app](https://fivestarport.vercel.app)** を開き、GitHubにサインインして3つのファイルを選ぶだけ。約25分後には、インストールできるアプリが完成します。無料です。

### 3分間のチュートリアルを見る

https://github.com/user-attachments/assets/1efff2dc-675e-473d-b988-0c23784404ed

GTA VのWebAssembly版をiPhone上でネイティブ実行するファンプロジェクトです。エンジンをARM64にコンパイルし、すべてのシェーダーを事前コンパイルしたネイティブのMetalレンダラーを使用します。ストーリーモードや自由に探索できるサンドボックス、実際のコントローラーとして動作するタッチ操作（ゲーム本来のエイムアシストに対応）、ジャイロ照準、端末の傾きによるステアリング、ネイティブに近い解像度まで対応するグラフィックプリセットを備えています。

**このリポジトリには、ゲームファイルもゲーム本体のコードも含まれていません。** ご自身でゲームファイルを用意する必要があります。それらのファイルから、ご自身のGitHubアカウント内（またはご自身のMac上）でアプリをビルドし、iPhone上にあるご自身のゲームファイルを使ってプレイします。

> Rockstar GamesおよびTake-Two Interactiveとは関係がなく、両社の承認も受けていません。権利者の方は kevin@aether.ee までご連絡ください。速やかにリポジトリを削除します。

## 必要なもの

| | |
|---|---|
| **ご自身のゲームファイル** | Web版ビルド `8b0b5899ed`：`data/` と `b/8b0b5899ed/` を含むフォルダ。約21 GB。 |
| **メモリ6 GBのiPhone** | iPhone 12 Pro、13 Pro、またはiPhone 14以降の各モデル。iOS 17以降と、約30 GBの空き容量が必要です。メモリ4 GBの古いiPhoneでは、メモリ不足になる可能性が高いです。 |
| **GitHubアカウント**（無料） | アプリのビルドに使用します。クレジットカードは不要です。 |
| **SideStoreまたはAltStore**（無料） | 普段のApple IDでアプリをインストールします。初期設定時に一度だけパソコンが必要です（Appleの制約）。[SideStore](https://sidestore.io) · [AltStore](https://altstore.io) |

有料のAppleアカウントは必要ありません。

## 4つの手順でインストール

### 1. ゲームファイルをiPhoneに保存する

ゲームフォルダ（中に `data/` と `b/` があるフォルダ）をiPhoneにコピーし、「ファイル」アプリの **「このiPhone内」（On My iPhone）** に保存します。iCloud Driveではなく、このiPhone内に保存してください。iCloudは容量を節約するために端末上のファイルを削除することがありますが、このゲームはすべてのファイルが端末上にある必要があります。

フォルダを保存できれば、どの方法でも構いません。例えば次の方法があります。

- Macから **AirDrop** で送るか、「ファイル」アプリでダウンロードして展開します。
- **ケーブルで転送する場合** は、アプリのインストール後（手順3）に、MacのFinderまたはWindowsのAppleデバイスアプリを使います。iPhoneを選択して **「ファイル」（Files）** を開き、フォルダを **GTA V Port** にドラッグします。「ファイル」アプリの「このiPhone内 › GTA V Port」に表示されます。

### 2. 5★ Port Builderでアプリをビルドする

iPhoneで **[fivestarport.vercel.app](https://fivestarport.vercel.app)** を開き、次の手順に従います。

1. **GitHubを接続します（Connect GitHub）。** ビルダーが、ご自身のアカウント内にこのリポジトリのプライベートなコピーを作成します。GitHubから一度だけ承認を求められます。「All repositories」を選択したままにしてください。
2. ゲームフォルダから **3つのファイルを選択します。**
   - `b/8b0b5899ed/game.wasm`
   - `shaders.zip`：「ファイル」アプリで `b/8b0b5899ed` を開き、`shaders` フォルダを長押しして **「圧縮」（Compress）** をタップします。作成されたzipファイルを選択してください。
   - `data/manifest.json`
3. **アップロードしてビルドします（Upload and build）。** 約85 MBがご自身のプライベートリポジトリにアップロードされます。大容量の `data` フォルダはiPhoneに残ります。その後、GitHubが約25分でアプリをビルドします。ページを閉じて、後から戻ってきても構いません。

完了したら **Download my app（アプリをダウンロード）** をタップして `GTA5Port.ipa` を取得します。ファイルは、ご自身のGitHubリポジトリの「Releases」にも保存されます。

### 3. アプリをインストールする

**SideStore** または **AltStore** を開き、**My Apps** に移動して **+** をタップし、`GTA5Port.ipa` を選択します。無料のApple IDでは7日ごとにアプリを再署名する必要があります。SideStoreはiPhone上で、AltStoreはパソコンからWi-Fi経由で再署名します。

### 4. アプリにゲームファイルを指定してプレイする

**一番簡単な方法：** アプリを一度開いてから、「ファイル」アプリでゲームフォルダを長押しし、**「移動」（Move）** をタップして **「このiPhone内 › GTA V Port」** を選択します。「このiPhone内」での移動はすぐに完了します。アプリをもう一度開くと、ゲームを自動で検出します。フォルダの階層が深くても検出できるため、`mirror/playgta5.com/…` のような構成でもそのまま使えます。

**フォルダを選択する方法：** アプリ内の **Game files（ゲームファイル）** カードをタップし、**Choose a folder…（フォルダを選択）** から、どこかにゲームが含まれるフォルダを開きます。「このiPhone内」自体を選んでも構いません。アプリがその中を検索します。

**zipやrarファイルしかない場合：** アプリが展開できます。**Game files** 画面でファイルへの直接リンクを貼り付けるか、ダウンロードページのリンクを貼り付けます。ダウンロードページの場合は内蔵ブラウザーが開き、アプリがダウンロードを引き継ぎます。「ファイル」アプリからアーカイブを選択することもできます。ダウンロードしながら展開するため、必要な空き容量は約21 GBで、その倍の容量は必要ありません。

どの方法でも、アプリはプレイ前にすべてのゲームファイルを確認し、不足や破損があるファイルを具体的に知らせます。

その後、**Story mode（ストーリーモード：セーブ可能なキャンペーン）** または **Sandbox（自由探索）** を選択し、**Play（プレイ）** を押します。

すべてiPhone上で実行されるため、プレイ中にサーバーやインターネット接続は必要ありません。

## ヒント

- **グラフィック：** Settings（設定）にはBatteryからMaxまで6種類のプリセットがあり、解像度は別に設定できます。解像度はプレイ中でも変更できます。推奨より高いプリセットを選ぶと警告が表示されます。設定に必要なメモリが、iPhoneからアプリに割り当てられる量を超えるとゲームが終了します。次回の起動時にアプリがそのことを知らせ、動作する設定に戻します。すでに端末上で正常に動作した設定を下げることはありません。
- **問題が起きた場合：** Settings › **Send log to the developer（開発者にログを送信）** で、今回の実行ログと前回のログ（クラッシュ時のログ）をワンタップで送れます。**Share log（ログを共有）** では、自分で保存したり送信したりできます。
- **操作：** **Edit controls layout（操作レイアウトを編集）**（スタート画面またはSettings）から、各タッチボタンの移動・サイズ変更・非表示を設定できます。エイムアシスト、ジャイロ照準、傾きによるステアリングはSettingsで設定します。Bluetoothコントローラーにも対応し、接続中はタッチ操作が非表示になります。
- **更新：** 新しいバージョンが公開されたら、ビルダーをもう一度開いて **Build again（再ビルド）** をタップします。ゲームフォルダとセーブデータはそのまま残ります。

## パフォーマンスを最大限に引き出す

最も効果が大きいのは **使用できるメモリを増やすこと** です。iOSは通常、iPhoneのRAMの約半分をアプリに割り当てるため、グラフィック設定に制限が生じます。次の方法で、無料で使用可能なメモリを増やせます。

### SideStore + GetMoreRamで使用可能なメモリを増やす（無料）

プレイヤーからは、この方法がうまく動作し、プレイしやすさが大幅に改善したという報告があります。

1. [fivestarport.vercel.app](https://fivestarport.vercel.app) で、Upload and buildをタップする前に **Enable increased memory entitlements（メモリ上限を増やす権限を有効化）** にチェックを入れます。すでにビルド済みの場合は、チェックを入れて **Build again** をタップしてください。
2. 新しい `GTA5Port.ipa` を、通常どおり **SideStore** でインストールします。
3. **[GetMoreRam](https://github.com/hugeBlack/GetMoreRam)** をインストールし、SideStoreで使っているものと **同じApple ID** でサインインします。**GTA V Port** を選択して **Increased Memory Limit** を追加します。
4. SideStoreでGTA V Portを **更新（refresh）** し、変更を反映します。
5. アプリを開くと、**Settings** の下部にメモリ上限が表示されます。以前より明らかに増えているはずです（例えば、メモリ6 GBのiPhoneで約3,500 MBを超える値）。

有料のApple DeveloperアカウントまたはTrollStoreでも、GetMoreRamを使わずに同じ効果が得られます（後述の「無料と有料のAppleアカウントの違い」を参照）。

### 次にゲームの設定を調整する

- **グラフィックプリセット：** メモリが増えたら、1段階高いプリセット（Balanced、Quality、Ultra）を試してください。負荷が大きすぎる場合は、次回の起動時にアプリが知らせて設定を下げるため、安心して試せます。
- **解像度：** プレイ中にSettingsで個別に設定できます。画面の鮮明さとフレームレートのバランスを調整する、最も重要な設定です。
- **フレームレート：** Settings › Frame rateで設定します。**30** は最も安定し、発熱も抑えられます。**60** はより滑らかです。**Unlocked（上限なし）** では、ProMotion搭載iPhone（13 Proおよびそれ以降のProモデル）で最大120 FPSになります。次回の起動時に反映されます。
- **端末を冷やす：** iPhoneは熱くなると処理速度が低下します。ケースを外すか風通しのよい場所でプレイし、熱くなる場合はプレイ中の充電を避けてください。
- プレイ前に **ほかのアプリを閉じ**、**低電力モードをオフ** にしてください。
- **ゲームファイルはiPhone内に保存：** ゲームフォルダはiCloud Driveではなく *「このiPhone内」* に置いてください。iCloudが端末上のファイルを削除すると、読み込み時に引っかかる原因になります。

## 更新情報

各バージョンの変更内容は [CHANGELOG.md](CHANGELOG.md) をご覧ください。

## コミュニティとサポート

**[TelegramのFive Star Port](https://t.me/fivestarport)** では、インストールの相談、ビルドログの共有、不具合の議論ができます。非公式のコミュニティ運営グループで、開発者自身はあまり確認していません。急ぎで開発者に連絡する必要がある場合は、Xの [@kevinerikjs](https://x.com/kevinerikjs) にDMを送ってください。

不具合は、このリポジトリの [Issues](https://github.com/kevinerikjs/gta5-ios-port/issues) でも報告できます。Settings › Share logから取得したログを添付してください。

---

## ほかのビルド方法（上級者向け）

上記のビルダーを使う方法が最も簡単です。以前からある次の方法も引き続き利用できます。

### ご自身のMacでビルドする

Apple Silicon搭載Mac、Xcode（無料）、および `brew install xcodegen` でインストールするXcodeGenが必要です。スクリプトにゲームフォルダのパスを指定します。

```sh
./build_ipa.sh --mirror /path/to/your/game-folder          # 無料のApple ID
./build_ipa.sh --mirror /path/to/your/game-folder --paid   # 有料の開発者アカウント
```

約30〜60分で、スクリプトと同じ場所に `GTA5Port.ipa` が作成されます。SideStoreまたはAltStoreでインストールしてください。Xcodeから直接インストールする場合は、スクリプトが生成した `app/PlayGTA5Native.xcodeproj` を開き、実行先にご自身のiPhoneを選びます。**Signing & Capabilities** でApple IDを選択し（無料アカウントは *Personal Team* として表示されます。Xcodeに求められた場合は、バンドル識別子を一意の値に変更してください）、**Run** を押します。

### GitHub Actionsを自分で設定し、パソコンからストリーミングする

v1.0で使われていた方法です。パソコンから [Tailscale](https://tailscale.com)（無料）経由でゲームファイルを配信し、GitHubがそれらを使ってビルドします。プレイ中はアプリがファイルをストリーミングで読み込みます。iPhoneに21 GBのファイルを保存したくない場合に便利です。

[![v1.0のセットアップ動画（ストリーミング方式）](docs/video-thumbnail.jpg)](https://github.com/kevinerikjs/gta5-ios-port/releases/download/v1.0/gta5-ios-port-tutorial.mp4)

*この方式を説明する、70秒間のv1.0セットアップ動画です。*

**ゲームファイルを配信する**

1. パソコンとiPhoneにTailscaleをインストールし、両方で同じアカウントにサインインします。
2. Tailscaleの管理コンソールで **DNS** を開き、**MagicDNS** と **HTTPS Certificates** を有効にします。
3. パソコンでゲームフォルダ（`data/` と `b/` を含むフォルダ）を共有します。
   ```sh
   tailscale serve --bg "/path/to/your/game-files"
   ```
4. `tailscale serve status` を実行します。`https://my-pc.tailnet-name.ts.net` のようなサーバーアドレスが表示されます。iPhoneのSafariで `https://my-pc.tailnet-name.ts.net/data/manifest.json` を開き、テキストが表示されれば動作しています。

アクセスできるのは、ご自身のtailnet内の端末だけです。共有を停止するには `tailscale serve --https=443 off` を実行します。

**ビルドする**

1. このリポジトリのページで **Use this template › Create a new repository** を押し、**Private** を選択します。完成したアプリにはご自身のファイルから生成したゲームエンジンが含まれるため、公開リポジトリのコピーではビルドが実行されません。
2. Tailscaleの管理コンソールで **Settings › Keys › Generate auth key** を開きます。**Reusable** と **Ephemeral** を有効にし、有効期限を7日間など短めに設定して、キーをコピーします。
3. 作成したリポジトリで **Settings › Secrets and variables › Actions › New repository secret** を開きます。`TS_AUTHKEY`（コピーしたキー）と `GAME_SERVER_URL`（サーバーアドレス。例：`https://my-pc.tailnet-name.ts.net`）を追加します。
4. **Actions › Build my IPA › Run workflow** を開き、ゲームファイルの取得元を **my server (Tailscale)** に設定します。有料アカウントを持っている場合にのみ、*paid account* にチェックを入れてください。
5. 約25分後、リポジトリの **Releases**（またはワークフロー実行のアーティファクト）から `GTA5Port.ipa` をダウンロードします。

この方式はMacでも使えます：`./build_ipa.sh https://my-pc.tailnet-name.ts.net`。

**プレイする：** Tailscaleを接続したままにしてください。アプリはサーバーアドレスが入力された状態で開きます。初回の起動時に約4 GBがアプリ内にダウンロードされ、2回目以降は起動が大幅に速くなります。Settings › Game files › **Download all game files（すべてのゲームファイルをダウンロード）** で、ゲーム全体（約21 GB）をiPhoneにコピーすると、ストリーミングが不要になります。

### ビルド時間と料金

プライベートリポジトリには、毎月無料のGitHub Actions実行時間が付与されます（無料プランでは2,000分）。Macでの実行時間は10倍として計算されるため、25分のビルド1回で約250分を消費します。無料で実行できるのは、およそ月8回です。GitHubから料金が請求されるのは、支出上限を0より大きく設定した場合だけです。アカウントに過去の請求に関する問題が残っている場合、すべての実行が *startup_failure* ですぐに失敗します。GitHubの請求設定で解消してください。

## 無料と有料のAppleアカウントの違い

| | 無料のApple ID | 有料のApple Developerアカウント（年額99米ドル） |
|---|---|---|
| 動作 | 可能 | 可能 |
| iOSがアプリに許可するメモリ | 通常の上限（メモリ6 GBのiPhoneで約3,000 MB） | *Increased Memory Limit* + *Extended Virtual Addressing*（約4,000 MB） |
| プレイ体験 | 軽めのプリセットで滑らかに動作：iPhone 13 Pro Maxで約25〜31 FPS | 同様の動作に加え、より高いプリセットを使用する余裕がある |
| 再署名 | 7日ごと | 年1回 |

Settingsの下部に、iOSがアプリに割り当てたメモリ上限が表示されます。

**有料アカウントを使う場合：** ビルダーの *Enable increased memory entitlements* にチェックを入れるか、Macで `--paid` を指定し、有料の開発者チームで署名します。Macを使う方法が最も確実です。`app/PlayGTA5Native.xcodeproj` を開き、**Signing & Capabilities** で有料のチームを選択します。バンドル識別子を一意の値（例：`com.yourname.gta5port`）に変更し、**Increased Memory Limit** と **Extended Virtual Addressing** が一覧にあることを確認して、iPhoneを選び、**Run** を押します。SideStoreまたはAltStoreで有料のApple IDを使って署名したIPAでも無料アカウントのメモリ上限が表示される場合は、署名ツールがこれらの権限を削除しています。Macを使う方法に切り替えてください。

## 仕組み

- エンジン（ご自身のファイルに含まれる `game.wasm`）は、ビルド時に [wasm2c](https://github.com/WebAssembly/wabt) でCに変換し、ARM64にコンパイルします。iOSでは端末上でコードをコンパイルできません。
- グラフィックには、このプロジェクト独自のMetalレンダラー（`app/Source/MetalRenderer`）を使います。ゲームのDirect3D 11形式のコマンドストリームを、Metal上で直接実行します。ビルド時に、ご自身のゲームファイルに含まれるシェーダーを `app/ShaderTool` でMetal用に変換し、アプリに事前コンパイルして組み込みます。このツールはGoogleの [Tint](https://dawn.googlesource.com/dawn) を基にしており、ライセンスはBSD-3-Clause/Apache-2.0です。ビルド済みのツールは、このプロジェクトのリリースで提供しています。プレイ中に端末上でコンパイルするものはありません。
- タッチ入力をエンジン本来のコントローラー処理に渡すため、GTAのコントローラー向け機能（エイムアシスト、アナログ入力による運転）が動作します。
- ゲームファイルはiPhone内のフォルダから直接読み込むか、ご自身のサーバーからブロックキャッシュへストリーミングで読み込みます。
- Webビルダーは、ご自身のGitHubアカウントでサインインしたブラウザー上で動作します。ビルドに必要な3つのファイルをプライベートリポジトリにアップロードし、そのリポジトリ内で、このリポジトリのワークフローを実行します。ビルダーのサーバーには何も保存されません。

## ライセンス

このプロジェクトのために書かれたコードはMITライセンスです（`LICENSE` を参照）。ゲーム本体、ゲームデータ、およびビルド時に取得するサードパーティーのファイルは、このライセンスの対象ではありません。
