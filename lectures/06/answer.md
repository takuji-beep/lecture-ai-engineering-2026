# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前：
[glossary_search_glossary]
- STEP 2 の [tool call]：
[server] glossary: コマンドで起動（uv run python -m app.mcp_server）
- STEP 3 の [tool call]：
[server] glossary: コマンドで起動（uv run python -m app.mcp_server）
[server] fetch: コマンドで起動（uvx mcp-server-fetch==2026.11.11 --no-readability-js）
- STEP 4 の [tool call]：
[server] glossary: コマンドで起動（uv run python -m app.mcp_server）
[server] fetch: コマンドで起動（uvx mcp-server-fetch==2026.11.11 --no-readability-js）
[server] aws: URL に接続（https://knowledge-mcp.global.api.aws）
- 気づき・疑問：
演習で実施した内容について、実際に作業を確認することができ、自分でMPCサーバーを立てるという作業がいかに簡単にできるか実感することができた。また、１０年前にAPIで接続して情報を引き出すことに数日かかったのが、数行でできてしまって大変感動した。


## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎
- やったこと：
以下をmpc_server.pyについて
 TODO(宿題・基礎): get_lecture_summary も公開しようget_lecture_summary
server.tool()(tools.get_lecture_summary)

実施内容
●　質問に本講義でAWSを使うメリットを聞き、AWSのmpcと講座の中身を確認するか質問を行った
　「AIE2026ではAWSを用いたAIエンジニアリングを実施していますが、その効果についてAWSの特徴を踏まえて３行程度で教えてください」
uv run python -m app.mcp_agent --trace "AIE2026ではAWSを用いたAIエンジニアリングを実施していますが、その効果についてAWSの特徴を踏まえて３行程度で要約して教えてください"
- 結果：

　AIEを無視して「AWSの特徴を踏まえて３行程度」のみだった
- 回答引用
　AWSを活用したAIエンジニアリングでは、Amazon Bedrockなどのフルマネージドサービスにより、多様な基盤モデル（FMs）へ柔軟かつ迅速にアクセスできる点が大きな効果です。
また、高い拡張性や堅牢なセキュリティ、プライバシー保護を備えており、インフラ管理の負担を軽減しながら安全で実用的な生成AIアプリケーションを効率よく開発・スケールさせることができます。

- 再度講義資料を呼び出すように指示
uv run python -m app.mcp_agent --trace "第１回～５回までの講義資料を分析し、AWSのMCPを用いる効果について３行程度で要約 して教えて ください"

- 再回答
　AIエンジニアリング講座（AIE2026）の第1回〜第5回の内容を分析すると、AWS（Amazon Web Services）などの外部サービス固有のMCP（Model Context Protocol）活用については、第3回などで扱う「AIエージェントに外部のツールやデータソースを標準的なプロトコルで安全につなぐ」という文脈（MCPサーバーの利用）に位置づけられます。

AWSのMCPを用いる主な効果を3行程度で要約すると、以下のようになります。

1. **外部リソースやAWS上のデータ・ツールへの標準化されたアクセス**により、モデルが自律的に適切な情報を取得・操作できるようになる。
2. **AIエージェントの適用範囲が大きく拡大**し、静的な知識にとどまらない動的かつ実用的なシステム構築が可能になる。
3. **独自のエージェント実装を共通化**できるため、多様なLLMやクライアントから一貫した方法でツール群を安全に利用できるようになる。

- 気づき・疑問：
　質問（プロンプト）を変えるだけで、まったく異なる動作となり、実際に基礎で足した、内容をきちんと引用しつつ回答できた。他方、AWSのMCPを呼び出したかったものの、うまくいかず、質問の内容（ツールの評価）の大切さを感じた。