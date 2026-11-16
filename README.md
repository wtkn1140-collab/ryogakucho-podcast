# 両学長 リベラルアーツ大学 音声版

YouTube「両学長 リベラルアーツ大学」（@ryogakucho）の本編動画（切り抜き・再放送を除く）を音声化し、Apple Podcasts で聴けるようにする仕組み。
構成は `~/claude/doctorlearning-podcast` と同じ（取得は Mac、配信は GitHub Pages）。

## スマホで聴く
- フィード: https://wtkn1140-collab.github.io/ryogakucho-podcast/feed.xml
  （Apple Podcasts → ライブラリ →「…」→「URLで番組をフォロー」）
- プレーヤー: https://wtkn1140-collab.github.io/ryogakucho-podcast/

## Mac 側
- 自動実行: `~/Library/LaunchAgents/com.ryogakucho.podcast.plist` → `run.sh`（2時間ごと）
- ログ: `logs/update.log`
- 手動で今すぐ取得: `./run.sh`
- 自動実行を止める: `launchctl bootout gui/$(id -u) ~/Library/LaunchAgents/com.ryogakucho.podcast.plist`
- 最新15本は `audio-site/`（ryogakucho-podcast-audio）、それより前（最新100本まで）は `archive1/`〜（ryogakucho-podcast-archiveN）
- 題名は日本語で取得するため `youtube:lang=ja` を指定している
- 題名に「切り抜き」「再放送」を含む動画は対象外（`podcast.py` の `EXCLUDE_WORDS`）
