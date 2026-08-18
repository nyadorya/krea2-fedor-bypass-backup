# krea2-fedor-bypass-backup

Krea 2 向けLoRAの個人バックアップ集。

## 経緯

もともと[Krea2FilterBypass](https://civitai.com/models/2192970)
(modelVersionId `3067151`)を使用していたが、2026-08-18時点でCivitai側が当該バージョンを
Early Access化し、通常のAPIトークンではダウンロード不能(`HTTP 403 "This asset is in
Early Access"`)になった。代替として同等の効果を持つ
[Krea2 Filter Bypass \[Fedor\]](https://civitai.com/models/2746817?modelVersionId=3089754)
に切り替えたが、配布元(Civitai/HuggingFace)が将来同様の理由でアクセス不能になるリスクに
備え、現在使用しているLoRAの本体ファイルを自分用にバックアップする。

## ファイル

### fedor_bypass.safetensors
- 1040 bytes, sha256: `0f9e2350ce7d4da5e0f0dc8ae02bbf99f2db4c4143beae899f9f808fc26d7d2c`
- 2026-08-18にCivitai API(`https://civitai.com/api/download/models/3089754`)から取得
- 実機(vast.ai上のForge Neo + sd-forge-krea2)での動作を確認済み
  (`[LORA] Loaded fedor_bypass.safetensors for KModel-UNet with 1 keys at weight 1.0
  (skipped 0 keys)`)
- 出典: https://civitai.com/models/2746817/krea2-filter-bypass-fedor
  (作者本人のGitHub: https://github.com/CliffNodes/fedor_bypass)
- ライセンス(Civitai上の設定、2026-08-18確認): `allowCommercialUse: Image/RentCivit/Rent/Sell`,
  `allowNoCredit: true`, `allowDerivatives: true`, `allowDifferentLicense: true`
- 対象モデル: Krea 2(any variant)

### BreastSlider-KREA2.safetensors
- 10,088,216 bytes, sha256: `77b789ba95e24ccd450c535cc395d0a2120ca1ec9264b75d4bfc376155694dd6`
- 2026-08-18にCivitai API(`https://civitai.com/api/download/models/3071726`)から取得
- 出典: https://civitai.com/models/2732158(modelVersionId 3071726)
- ライセンス(Civitai上の設定、2026-08-18確認): `allowCommercialUse: Image/RentCivit/Rent/Sell`,
  `allowNoCredit: true`, `allowDerivatives: true`, `allowDifferentLicense: true`
- 対象モデル: baseModel表記は「Krea 2」。配布元sogni.aiのページでKrea 2 Turbo互換が明記

### huge_breasts_woman.safetensors
- 6,434,160 bytes, sha256: `9ab031aecaaf4bf695e735bd14be73c46cfd2cfba6670888c6b517a4d51ae053`
- 2026-08-18にHuggingFace(`https://huggingface.co/sazyou-roukaku/sazyou_LoRA/resolve/main/huge_breasts_woman.safetensors`)から取得
- 出典・ライセンス: https://huggingface.co/sazyou-roukaku/sazyou_LoRA
  (リポジトリライセンス: `creativeml-openrail-m`)
- 対象モデル: forge(SDXL系ベース)プロファイル用

## バックアップ見送り(出典記録のみ)

### BracingEvoMix_v1.safetensors
- 出典: https://huggingface.co/sazyou-roukaku/BracingEvoMix/resolve/main/BracingEvoMix_v1.safetensors
- サイズ: 約2.03GB(2,132,627,500 bytes、2026-08-18確認)
- forgeプロファイルのベースcheckpoint。GitHub無料枠のGit LFS(ストレージ1GB・帯域1GB/月)を
  超過するため、本体のバックアップは見送り。URLのみ記録。

## 用途

vast.ai上でForge Neoを起動する個人用CLIでの利用を想定した個人バックアップ。
`models/Lora/` に配置し、`<lora:ファイル名:強度>` のようにプロンプトタグで使用する。
