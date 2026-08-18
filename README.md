# krea2-fedor-bypass-backup

Krea 2 向けの safety-filter bypass LoRA「Fedor Bypass」の個人バックアップ。

## 経緯

もともと[Krea2FilterBypass](https://civitai.com/models/2192970)
(modelVersionId `3067151`)を使用していたが、2026-08-18時点でCivitai側が当該バージョンを
Early Access化し、通常のAPIトークンではダウンロード不能(`HTTP 403 "This asset is in
Early Access"`)になった。代替として同等の効果を持つ
[Krea2 Filter Bypass \[Fedor\]](https://civitai.com/models/2746817?modelVersionId=3089754)
に切り替えたが、Civitai上のモデルが将来同様の理由でアクセス不能になるリスクに備え、
自分用に本体ファイルをバックアップする。

## ファイル

- `fedor_bypass.safetensors`(1040 bytes, sha256: `0f9e2350ce7d4da5e0f0dc8ae02bbf99f2db4c4143beae899f9f808fc26d7d2c`)
  - 2026-08-18にCivitai API(`https://civitai.com/api/download/models/3089754`)から取得
  - 実機(vast.ai上のForge Neo + sd-forge-krea2)での動作を確認済み
    (`[LORA] Loaded fedor_bypass.safetensors for KModel-UNet with 1 keys at weight 1.0
    (skipped 0 keys)`)

## 出典・ライセンス

- Civitaiモデルページ: https://civitai.com/models/2746817/krea2-filter-bypass-fedor
- 作者本人のGitHubリポジトリ: https://github.com/CliffNodes/fedor_bypass
- 作者: Fedor
- 対象モデル: Krea 2(any variant)
- Civitai上のライセンス設定(モデルページAPI確認、2026-08-18時点):
  `allowCommercialUse: Image/RentCivit/Rent/Sell`, `allowNoCredit: true`,
  `allowDerivatives: true`, `allowDifferentLicense: true`
  (再配布・改変ともに許可される設定)

## 用途

vast.ai上でForge Neoを起動する個人用CLIでの利用を想定した個人バックアップ。
`models/Lora/` に配置し、`<lora:fedor_bypass:1.0>` のようにプロンプトタグで使用する。
