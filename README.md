# Hi there, I'm Ichiru Oda 👋

## 🚀 About Me
- 🎓 **日本電子専門学校 モバイルアプリケーション開発科** 在籍
- 📱 **Mobile App Developer**: iOS (SwiftUI) および Android (Java) をメインに開発しています。
- 🛠 **Focus**: これまでチーム開発におけるタスク管理（GitHub Issues）や、Figmaを用いた簡単なUI設計を経験してきました。
- 📝 **Certification**: 2026年7月末までに Java Silver の取得を目標に学習を継続中です。

---

## 🛠 Tech Stack

### Languages (Proficient to Learning)
![Java](https://img.shields.io/badge/Java-007396?style=flat-square&logo=java&logoColor=white)
![Swift](https://img.shields.io/badge/Swift-F05138?style=flat-square&logo=Swift&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![Shell](https://img.shields.io/badge/Shell_Script-4EAA25?style=flat-square&logo=gnu-bash&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

### Frameworks & Tools
![SwiftUI](https://img.shields.io/badge/SwiftUI-007ACC?style=flat-square&logo=Swift&logoColor=white)
![Figma](https://img.shields.io/badge/Figma-F24E1E?style=flat-square&logo=Figma&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=Git&logoColor=white)
![GitHub Issues](https://img.shields.io/badge/GitHub%20Issues-181717?style=flat-square&logo=github&logoColor=white)

---

## 📂 Featured Projects

### 🎥 [yt-mac-menu](https://github.com/Progate-Hackathon/yt-mac-menu) (Progate Hackathon)
指パッチンでカメラ起動、ジェスチャーでショートカットやGitCOMMIT＆PUSHを実行する、Macのメニューバー常駐アプリ。
- **Role**: UI実装 / GitHub Issuesによるタスク管理
- **Stack**: Swift (SwiftUI), GitHub Issues
- **Insight**: AIを搭載したジェスチャーショートカットソフト、5人チームでGitHubIssueによるタスク管理をして開発

### 🍎 [GourmeSearch](https://github.com/25cm0109-OD/Gourmesearch)
Hot Pepper Gourmet Search APIを活用した、飲食店検索iOSアプリ。
- **Stack**: SwiftUI, URLSession
- **Insight**: MVアーキテクチャを使用したホットペッパーグルメサーチAPIを叩いて位置を表示するマップアプリを制作


---

## 📫 Contact
- **Location**: Shinjuku, Tokyo
- **GitHub**: [https://github.com/25cm0109-OD](https://github.com/25cm0109-OD)



/**
 * ====================================================================
 * 1. コードの説明 (README) / 設計思想・技術的考慮
 * ====================================================================
 * * ## 1. 設計意図 (Why So?)
 * * ### ターゲットユーザーの課題（ペルソナとインサイトの深掘り）
 * 本設計にあたり、初めてアルバイト探しをする10代のリアルな課題を抽出するため、
 * 実際に「自宅周辺のバイトに落ち続けて困っている」「接客などのコミュニケーション能力を
 * 必要とする仕事は怖いから行きたくない」という悩みを抱えている私の友人をベースにペルソナを設定し、
 * インサイトを深掘りしました。
 * * その結果、従来の求人サイトのような単なる条件検索（距離が近い順など）では解決できない、
 * 以下のような「心理的・身体的ハードルのグラデーション」があることが分かりました。
 * * 1. 職種に対する心理的恐怖（精神的苦痛）：
 * 「接客が苦手」「コンビニなどのマルチタスクは失敗しそうで怖い」という強い不安があり、
 * 多少条件が良くても精神的負担が大きい仕事は避けたい。
 * 2. 移動に対する心理的・体力的ハードル（肉体的苦痛）：
 * 「休日に働く際、電車に乗って2駅先まで行くのは気力が出ないため極力避けたい。
 * できれば最寄り（徒歩・自転車圏内）が良い」という本音。
 * 3. 優先順位の逆転（インサイト）：
 * ここで重要なのは、「精神的苦痛（接客）」＞「肉体的苦痛（2駅先の移動）」という優先度になっている点です。
 * つまり、「最寄りの接客あり」で妥協するくらいなら、「2駅先でも、自分のペースで黙々とできる接客なし（軽作業など）」
 * のほうが心理的負担が少ないため、そちらを選ぶという行動特性が見えてきました。
 * * ### 提案する解決アプローチ（なぜこの機能をプッシュ通知・アプリで提供するのか）
 * バイトに落ち続けて自信を失っているユーザーは、メンタル的にも「能動的に求人を探す気力」自体が減退しています。
 * さらに、今回のターゲットが求めている「コミュニケーションが少なくて自宅から近い良質な求人」は、
 * 市場において非常に人気が高く、掲載されてからすぐに枠が埋まって無くなってしまう（争奪戦になる）という問題があります。
 * * ユーザーがアプリを開いていない受動的な状態であっても、バックエンド側で条件に合致する理想的な求人を検知した瞬間に
 * プッシュ通知を届けることで、「自分から探すストレスをゼロにしつつ、人気の良質求人が消えてしまう前に最速で気付ける体験」
 * をアプリ特有の価値として提供します。
 * * ### スコアリング（優先順位）の定義
 * - 1位（100点）: 最寄り駅周辺（1km以内） × 接客なし（黙々作業） 
 * -> 「近いし自分でもできそう！最高」というベストな選択肢。
 * - 2位（80点） : 1駅先（1〜2km） × 接客なし
 * -> 「少し歩く・自転車を使うが、接客がないなら全然アリ」という現実的な選択肢。
 * - 3位（60点） : 2駅先（2〜3.5km） × 接客なし
 * -> 「電車移動の面倒さはあるが、精神的に楽なので頑張れる」という許容範囲。
 * - 4位（40点） : 最寄り駅周辺（1km以内） × 接客あり
 * -> 「接客は嫌だが、家から超近いからワンチャン…」という最終妥協ライン。
 * * ※それ以外の「遠くて接客あり」の求人は、ターゲットにとって行く意味が全くない「ノイズ」となるため、
 * スコア0（非表示）として徹底的に排除します。これにより、ユーザーの「選べない」という課題を根本から解決します。
 * * ---
 * * ## 2. 技術的考慮と実現性 (So What?)
 * * ### ① パフォーマンスと効率（月間1億回アクセス・10万件データ対策）
 * ユーザーがアプリを開くたびに10万件のデータから「距離」と「職種」の掛け算をリアルタイム計算すると、
 * DB負荷でサーバーが即座にダウンします。
 * - 対策: スコア計算はAPIリクエスト時ではなく、深夜および新着求人追加時の「事前バックグラウンドバッチ処理」で行います。
 * 計算結果の上位3件のIDリストのみをメモリキャッシュ（Redis）に格納。
 * - 効果: API側はRedisからデータを秒速で引いて返すだけ（O(1)の処理）になるため、月間1億アクセスを最小限の
 * サーバーリソースで高速にさばけます。また、返却データも3件分のIDに基づく最小限のテキストのみに絞り、
 * モバイル回線の通信量を大幅に削減しています。
 * * ### ② ネイティブアプリ特有の考慮
 * * #### バージョニングと互換性の担保
 * アプリはWebと違い、ユーザーが古いバージョンのまま使い続けるケースが多々あります。
 * - 対策: 既存の `GET /api/recommendations` はそのまま残し、今回の新機能を `GET /api/v2/...` として
 * エンドポイントを新設・分離しました。これにより、古いアプリを強制アップデート（クランクアップ）
 * させることなく、安全に新しい推薦ロジックを提供できます。
 * * #### バッテリー消費とバックグラウンド処理の配慮
 * スマホのGPSを常に起動してリアルタイムに現在地を追従すると、端末のバッテリーを激しく消耗します。
 * - 対策: 今回の機能では、アプリ側から都度GPS座標を送信させるのではなく、ユーザーの「プロフィール（自宅最寄り駅や
 * 自宅座標）」をサーバー側に保持し、それを基準に計算します。アプリ側の位置情報取得は最小限（設定時のみ等）
 * に抑えられ、端末のバッテリー消費を防ぎます。
 * * #### プッシュ通知のノイズ・負荷対策
 * 「人気の求人を逃さない即時性」は重要ですが、100万人に一斉プッシュ通知を行うと、通知サーバーや、
 * 通知を開いた瞬間のスパイクアクセスでシステムがパンクします。また、無関係な通知はアプリ削除に繋がります。
 * - 対策: 今回のスコアリングで「スコア80点以上（1駅先以内の接客なし）」の新着案件がヒットしたユーザーのみを
 * SQL/Redis側で厳密にセグメント抽出し、対象者だけに絞って通知を生成します。さらに、AWS SQSなどの
 * メッセージキューを用いて非同期で段階的に分散配信することで、システム負荷の平準化と、ユーザーにとって
 * 「本当に有益な情報」としての通知を両立させます。
 */


/**
 * ====================================================================
 * 2. 実装ソースコード (Node.js / Express想定)
 * ====================================================================
 */

// おすすめ求人取得API (v2として新設: モバイルアプリの互換性を担保)
// GET /api/v2/recommendations/low-effort
app.get('/api/v2/recommendations/low-effort', async (req, res) => {
    try {
        const userId = req.user.id; 

        // 1. [パフォーマンス対策] リアルタイム計算を避け、キャッシュ(Redis)からデータを引く
        const cachedJobIds = await redis.get(`user:${userId}:recommendations`);

        let jobIds = [];
        if (cachedJobIds) {
            jobIds = JSON.parse(cachedJobIds);
        } else {
            // キャッシュが万が一無い場合のセーフティ（最低限の最新求人をDBから取得）
            jobIds = await getFallbackJobIds(userId);
        }

        // 2. 厳選されたID(最大3件)のみをピンポイントで引くため超高速
        const jobs = await db.table('jobs')
            .whereIn('id', jobIds)
            .select('id', 'title', 'company_name', 'job_type'); // [通信量削減] 必要なカラムのみに絞る

        // 3. モバイル向けに軽量化したレスポンスを返却
        return res.status(200).json({
            status: "success",
            data: {
                recommendations: jobs
            }
        });

    } catch (error) {
        console.error(error);
        return res.status(500).json({ status: "error", message: "Internal Server Error" });
    }
});


/**
 * 毎日深夜（および新着求人追加時）に裏側で実行される「おすすめスコアリング計算バッチ」のロジック
 * (10万件の求人 × 100万人のユーザーの総当たり計算をバックグラウンドで処理)
 */
async function runDailyScoringBatch() {
    // ユーザーの自宅位置情報を取得
    const users = await db.table('user_profiles').select('user_id', 'home_latitude', 'home_longitude');
    
    for (const user of users) {
        // ユーザーの自宅近辺（例: 半径5km以内）かつ「接客なし」または「最寄り駅1km以内」の候補求人をDBから高速に一括取得
        const candidateJobs = await db.table('jobs')
            .where('is_contactless', true)
            .orWhere(db.raw('ST_Distance_Sphere(point(longitude, latitude), point(?, ?)) <= 1000', [user.home_longitude, user.home_latitude]));

        const scoredJobs = candidateJobs.map(job => {
            // ユーザーの自宅と求人情報の直線距離を計算（単位: km）
            const distance = calculateDistance(user.home_latitude, user.home_longitude, job.latitude, job.longitude);
            
            let score = 0;
            if (distance <= 1.0 && job.is_contactless) score = 100;                      // 1位: 最寄り × 接客なし
            else if (distance > 1.0 && distance <= 2.0 && job.is_contactless) score = 80; // 2位: 1駅先 × 接客なし
            else if (distance > 2.0 && distance <= 3.5 && job.is_contactless) score = 60; // 3位: 2駅先 × 接客なし
            else if (distance <= 1.0 && !job.is_contactless) score = 40;                 // 4位: 最寄り × 接客あり

            return { job_id: job.id, score: score };
        });

        // スコアが高い順にソートし、上位3件のIDだけを抽出
        const top3JobIds = scoredJobs
            .filter(j => j.score > 0)
            .sort((a, b) => b.score - a.score)
            .slice(0, 3)
            .map(j => j.job_id);

        // 前回のキャッシュと比較するために現在のキャッシュを取得
        const previousCache = await redis.get(`user:${user.user_id}:recommendations`);
        
        // 新しいおすすめデータをRedisに保存（有効期限24時間）
        await redis.set(`user:${user.user_id}:recommendations`, JSON.stringify(top3JobIds), 'EX', 86400);

        // [即時性の担保] 争奪戦になる「接客なし×地元」の新規好条件案件を逃さないよう、非同期でプッシュ通知キューに登録
        if (hasNewHighPriorityJob(previousCache, top3JobIds)) {
            await pushNotificationQueue.add({
                userId: user.user_id,
                title: "あなたにぴったりの新着求人！",
                body: "「接客なし×自宅近く」の好条件バイトが届いています。枠が埋まる前にチェック！"
            });
        }
    }
}

