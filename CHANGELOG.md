# 変更履歴 (Changelog)

すべての重要な変更はこのファイルに記録されます。

---

## v1.0.0 - 2026-11-14

🎉 **初期リリース (Initial Release)**

Windows 11 のスナップレイアウト・スナップアシスト・ドラッグ視覚効果の不整合をレジストリと Win32 API の両面から診断し、ワンクリックで一括修復・即時反映するスタンドアロンツール「Win11SnapAllInOne」のファーストリリースです。

**✨ 主な機能・特徴 / 新機能 (Added)**
- **スタンドアロン・ポータブル設計**: 単一の実行ファイル（`Win11SnapAllInOne.exe`）だけで起動可能。外部の .NET ランタイムのインストールやセットアップ作業は不要です。
- **レジストリ & Win32 API 実効値の同時スキャン**: 視覚効果（`DragFullWindows`）、ウィンドウ動作（`WindowArrangementActive` / `DockMoving` / `SnapSizing`）、スナップレイアウト（`EnableSnapBar` / `EnableSnapAssistFlyout`）、スナップアシスト（`SnapAssist` / `JointResize`）、ポリシー制限（`NoWindowMinimizingShortcuts`）の計 9 項目を一括診断します。
- **ワンクリック一括修復・即時反映**: レジストリの修復に加え、Win32 `SystemParametersInfo` API の更新、`WM_SETTINGCHANGE` ブロードキャスト、およびエクスプローラー（`explorer.exe`）の再起動（チェックボックスで切替可）により設定を即時反映します。
- **個別項目の ON / OFF 切替・再スキャン**: 一覧のダブルクリックまたは「選択項目を ON / OFF 切替」ボタンで設定ごとの切り替えが可能（ポリシー制限項目は一括修復で解除）。
- **ライト / ダーク / システム連動テーマ対応**: 画面右上の「表示テーマ」から「システム」「ライト」「ダーク」を切り替え可能（Windows 11 のシステムテーマ変更にもリアルタイム追従）。
- **競合常駐プロセスの自動検出**: 画面端ドラッグスナップに干渉しやすい常駐ツール（`PowerToys` / `PowerToys.FancyZones` / `AutoHotkey` / `DisplayFusion` / `AquaSnap`）の稼働状況を起動時・再スキャン時に自動確認します。
- **コマンドラインサイレント修復対応**: `/fix` または `--fix` 引数を付けて起動することで、GUI を表示せずに一括修復＋エクスプローラー再起動を実行できます。

**💻 動作要件 (System Requirements)**
- **OS**: Windows 11 (64-bit / x64) ※Windows 10 (64-bit) でも動作可能
- **ランタイム**: 追加ランタイム不要（.NET 8 Self-Contained 単一実行ファイル）
