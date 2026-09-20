# custom-posteffet-resoucepack-generator

Minecraft の `/posteffect` コマンドで使うシェーダーを、ノードをつないで組み立てられる単一HTMLのエディターです。作ったシェーダーはそのまま `/posteffect` 用のリソースパック（zip）として書き出せます。

ブラウザ内で完結し、サーバーには何も送信されません。インストールも不要で、`posteffect_shader_editor.html` を開くだけで使えます。

## 使い方

1. `posteffect_shader_editor.html` をブラウザ（Chrome など）で開く
2. 左側のノードカタログからノードをドラッグして配置し、つないでエフェクトを組み立てる
3. 右側のプレビューで結果を確認する
4. できあがったらリソースパック（zip）として書き出し、ワールドの `resourcepacks` に入れる
5. ゲーム内で `/posteffect add @s <名前空間>:<エフェクト名>` を実行する

## 制限事項

- 1つの `/posteffect` エフェクトにつき1パスのフラグメントシェーダーしか生成できません（複数パス構成の既存エフェクトは「完全再現」サンプルとして読み込み専用で扱います）。
- `minecraft:entity_outline` バッファは実機の `/posteffect` チェインから参照できない（バニラ本体の `entity_outline.json` 自身も同じ理由で読み込み拒否される）ことが実機ログで確認されているため、このツールでは対応するノードを提供していません。

## ライセンス

MIT License。詳細は [LICENSE](./LICENSE) を参照してください。
