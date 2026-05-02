# GPT's Modpack

軽量ミニゲーム **Hana's Ember Heist** を入れた packwiz 管理リポジトリです。

## 構成

- Minecraft: 1.21.1
- Loader: Quilt 0.30.0-beta.7
- 追加物: データパック中心
- 想定人数: 1〜2人
- 重さ: 常時動く処理はスコア計算だけなので軽め

## ミニゲーム: Hana's Ember Heist

小さなアリーナ内の採掘ポイントに立つと，毎秒 Ember が増えます。  
中央の金ブロック地帯は高得点ですが，狙われやすい危険地帯です。先に 40 Ember に到達するか，180 秒終了時点で高得点を目指します。

### 導入

このリポジトリには，ワールド用データパックを `datapacks/hana-ember-heist` に置いています。

packwiz は通常 `.minecraft` 直下へファイルを配置するため，このままだと新規ワールドへは自動適用されません。まずは次のどちらかで試してください。

#### ローカルワールドで試す

```bash
cp -r datapacks/hana-ember-heist ~/.minecraft/saves/<world-name>/datapacks/
```

Windows の Prism Launcher などでは，対象インスタンスの `.minecraft/saves/<world-name>/datapacks/` に `hana-ember-heist` フォルダをコピーしてください。

#### サーバーで試す

```bash
cp -r datapacks/hana-ember-heist /path/to/world/datapacks/
```

コピー後，ゲーム内またはサーバーコンソールで次を実行します。

```mcfunction
/reload
/function hana_ember_heist:admin/install
/function hana_ember_heist:game/start
```

## 操作コマンド

```mcfunction
/function hana_ember_heist:game/help
/function hana_ember_heist:admin/install
/function hana_ember_heist:game/start
/function hana_ember_heist:game/stop
/function hana_ember_heist:game/reset
```

## 今後の拡張候補

- Paxi や Open Loader 系のMODでデータパックを自動ロードする
- Lightman's Currency などの通貨MODと接続して，獲得点をショップ購入へ変換する
- アリーナを複数マップ化する
- タイマーや目標点を難易度別に切り替える
