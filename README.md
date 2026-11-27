# Releases

星拓工作室 / NuAster 專案的建置與發佈。這裡只放建置流程，不放原始碼。

| 專案 | Workflow | 成品位置 |
|---|---|---|
| vps-hub | `release-vps-hub.yml` | 本 repo 的 Releases，標籤 `vps-hub-vX.Y.Z` |
| live-CC | `release-live-cc.yml` | 本 repo 的 Releases，標籤 `live-cc-vX.Y.Z` |

## 發版

```sh
gh workflow run release-vps-hub.yml -R qwer2415wy/Releases -f version=1.2.3
gh workflow run release-live-cc.yml -R qwer2415wy/Releases -f version=v1.2.3
```

## 規則

- 建置記錄是公開的：會引用原始碼的指令一律把輸出導到不公開的檔案。
- 多個專案共用本 repo，不要依賴 `/releases/latest`；以標籤前綴辨認版本。
- 需要的 secret：`TOOLS_DEPLOY_KEY`（唯讀取原始碼）。發佈用 workflow 內建的 token。
