---
title: 応用WebRTC
type: docs
weight: 9
---

# WebRTCの応用

WebRTCの仕組みがわかったところで、いよいよWebRTCを使って構築してみましょう。この章では、WebRTC を使って人々が何をどのように構築しているかを探り、WebRTC で起こっている興味深いことをすべて学びます。WebRTC のパワーにはコストがかかります。プロダクショングレードの WebRTC サービスを構築することは困難です。本章では、そのような課題にぶつかる前に、その課題を説明します。

## ユースケース別

WebRTCは、Webブラウザ上で会議を行うための技術に過ぎないと多くの人が考えています。しかし、それだけではありません。
WebRTCはさまざまなユースケースに利用されています。常に新しいユースケースが登場しています。この章では、一般的なユースケースをいくつか挙げ、WebRTC がそれらにどのような変革をもたらしているかを説明します。

### 会議

会議は WebRTC の最初のユースケースです。このプロトコルには、他のプロトコルがブラウザで提供していないいくつかの必要な機能が含まれています。WebSocket で会議システムを構築しても、最適な条件であれば動作するかもしれません。現実のネットワーク環境で展開できるものを求めるのであれば、WebRTC が最適な選択です。

WebRTCは、メディアの輻輳制御とアダプティブ・ビットレートを提供します。ネットワークの状況が変化しても、ユーザーは最高の体験を得ることができます。開発者は、これらの条件を測定するために追加のコードを書く必要もありません。

参加者は、複数のストリームを送受信できます。また、それらのストリームはいつでも追加・削除できます。コーデックもネゴシエートされます。これらの機能はすべてブラウザが提供するもので、開発者がカスタムコードを書く必要はありません。

また、会議にはデータチャンネルの利点もあります。ユーザーはメタデータを送信したり、ドキュメントを共有できます。信頼性よりもパフォーマンスが必要な場合は、複数のストリームを作成して設定できます。

### 放送

放送業界では、WebRTC を利用した新しいプロジェクトが数多く登場しています。このプロトコルは、メディアの発行者と消費者の両方にとって多くの利点があります。

WebRTCはブラウザ上で動作するため、ユーザーは簡単に動画を公開できます。また、ユーザーが新しいクライアントをダウンロードする必要もありません。
ウェブブラウザがあれば、どんなプラットフォームでも動画を公開できます。パブリッシャーは、複数のトラックを送信し、いつでもそれらを修正／削除できます。これは、1つの接続につき1つのオーディオトラックと1つのビデオトラックしか許可されていなかった従来のプロトコルに比べて、大きな進歩です。

WebRTCは、開発者が遅延と品質のトレードオフをより細かくコントロールできるようにします。遅延が一定の閾値を超えないことがより重要な可能性があり、多少のデコードアーチファクトは許容したいと思うでしょう。メディアが到着したらすぐに再生するようにビューアを設定できます。TCP上で動作する他のプロトコルでは、これは簡単ではありません。ブラウザでは、データを要求してそれで終わりです。

### リモートアクセス

リモートアクセスとは、WebRTC を使って他のコンピュータに遠隔でアクセスすることです。リモートホストを完全に制御することもできますし、単一のアプリケーションだけを制御することもできます。 これは、ローカルのハードウェアでは処理できないような、計算量の多いタスクを実行するのに適しています。例えば、新しいビデオゲームやCADソフトウェアの実行などです。WebRTCは、3つの方法でこの分野に革命をもたらしました。

WebRTCは、世界的にルーティングされていないホストへのリモートアクセスに使用できます。NATトラバーサルを使えば、STUN経由でしか利用できないコンピュータにアクセスできます。これは、セキュリティやプライバシーの面でも優れています。ユーザーは、ビデオをインジェストや「ジャンプボックス」に通す必要がありません。また、NATトラバーサルは導入を容易にします。ポートフォワーディングや固定IPの設定を事前に心配する必要がありません。

このシナリオでは、データチャネルも非常に強力です。最新のデータだけを受け付けるように設定できます。TCPの場合、Head-of-lineブロッキングが発生する危険性があります。古いマウスクリックやキープレスが遅れて到着すると、後続のデータが受け入れられなくなります。
WebRTCのデータチャネルはこの問題に対処するように設計されており、失われたパケットの再試行を行わないように設定できます。また、バックプレッシャを測定して、ネットワークがサポートする以上のデータを送信していないことを確認することもできます。

WebRTCがブラウザで利用できるようになったことで、生活の質が大きく向上しました。セッションを開始するために、専用のクライアントをダウンロードする必要はありません。WebRTCを搭載したクライアントはますます増えており、スマートテレビには完全なウェブブラウザが搭載されています。

### ファイル共有と検閲回避

ファイル共有と検閲回避は全く異なる問題です。しかし、WebRTCはこの2つの問題を同じように解決します。それは、どちらも簡単に利用でき、ブロックするのが難しくなるということです。

WebRTCが解決する最初の問題は、クライアントの獲得です。ファイル共有ネットワークに参加するには、クライアントをダウンロードする必要があります。ネットワークが分散されていても、まずクライアントを入手する必要があります。 制限されたネットワークでは、ダウンロードはしばしばブロックされます。ダウンロードできたとしても、ユーザーがクライアントをインストール/実行できない場合もあります。WebRTCはすべてのWebブラウザで利用可能なので、すぐに利用できます。

WebRTCが解決する2つ目の問題は、トラフィックがブロックされることです。ファイル共有や検閲回避を目的としたプロトコルを使用している場合、それをブロックするのは非常に簡単です。 WebRTCは汎用プロトコルなので、これをブロックするとすべての人に影響が及びます。WebRTCをブロックすると、ネットワークの他のユーザーが電話会議に参加できなくなる可能性があります。

### IoT

IoTにはいくつかの異なるユースケースがあります。多くの人にとって、これはネットワークに接続されたセキュリティカメラを意味します。WebRTC を使用して、携帯電話やブラウザなどの他の WebRTC ピアにビデオをストリーミングできます。また、デバイスを接続してセンサーデータを交換するというユースケースもあります。LANに接続された2つのデバイスで、気候、騒音、光の測定値を交換できます。

WebRTCは、従来のビデオストリームプロトコルに比べて、プライバシーの面で非常に優れています。WebRTCはP2P接続をサポートしているので、カメラはビデオを直接ブラウザに送信できます。ビデオがサードパーティのサーバーに送られる必要はありません。ビデオが暗号化されていても、攻撃者は通話のメタデータから推測できます。

相互運用性は、IoT分野でのもう一つの利点です。WebRTCは、C#、C++、C、Go、Java、Python、Rust、TypeScriptなど、たくさんの異なる言語で利用できます。つまり、自分に最適な言語を使うことができるのです。また、2つの異なるクライアントを接続するために、独自のプロトコルやフォーマットを使用する必要もありません。

### メディアプロトコルブリッジング

既存のハードウェアとソフトウェアで動画を作成しているが、まだアップグレードできない。ユーザーが動画を見るために独自のクライアントをダウンロードすることを期待するのは不満です。そこで、WebRTC ブリッジを導入します。ブリッジは2つのプロトコルを変換するので、ユーザーは従来のセットアップでブラウザを使用できます。

開発者がブリッジするフォーマットの多くは、WebRTCと同じプロトコルを使用しています。SIPは一般的にWebRTCで公開されており、ユーザーはブラウザから電話をかけることができます。RTSPは、多くのレガシーセキュリティカメラで使用されています。どちらも同じ基本プロトコル（RTPとSDP）を使用しているので、計算コストをかけずに実行できます。ブリッジが必要なのは、WebRTC固有の機能を追加したり削除したりする場合だけです。

### データプロトコルブリッジング

Web ブラウザは、限られたプロトコルしか使用できません。使えるのは、HTTP、WebSocket、WebRTC、QUIC です。それ以外のプロトコルに接続するには、プロトコルブリッジを使用する必要があります。プロトコルブリッジとは、外国のトラフィックをブラウザがアクセスできるものに変換するサーバーのことです。よくある例は、ブラウザからSSHを使ってサーバーにアクセスすることです。WebRTCのデータチャネルには、競合製品と比べて2つの利点があります。

WebRTCのデータチャネルでは、信頼性の低い、順序のない配信が可能です。低レイテンシーが重要なケースでは、これが必要です。これはヘッドオブラインブロッキングと呼ばれるもので、新しいデータが古いデータによってブロックされてしまうことを避けるためです。例えば、マルチプレイヤーの一人称視点のシューティングゲームをプレイしているとします。プレイヤーが2秒前にどこにいたかなんて、本当に気になりますか？もしそのデータが間に合わなかったとしたら、何度も送信しようとしても意味がありません。信頼性のない、順序立てられていない配信では、データが到着したらすぐに受け取ることができます。

また、データチャネルにはフィードバック・プレッシャーがあります。これは、接続がサポートする以上の速度でデータを送信しているかどうかを教えてくれます。このような場合、2つの選択肢があります。 データチャネルをバッファリングして遅れてデータを配信するように設定するか、リアルタイムに到着していないデータをドロップするかです。

### 遠隔操作

遠隔操作とは、WebRTC のデータチャネルを使ってデバイスを遠隔操作し、そのカメラを RTP で送り返すことです。現在、開発者は WebRTC を介して遠隔地で車を運転しています。建設現場でロボットを操作したり、荷物を配達したりするのにも使われています。このような問題にWebRTCを使用するのは、2つの理由から理にかなっています。

WebRTCのユビキタス性により、ユーザーにコントロールを与えることが容易になります。ユーザーに必要なのは、Webブラウザと入力デバイスだけです。ブラウザは、ジョイスティックやゲームパッドからの入力にも対応しています。WebRTCは、ユーザーのデバイスに追加のクライアントをインストールする必要性を完全に排除します。

## 分散型CDN

分散型CDNは、ファイル共有のサブセットです。分散型CDNはファイル共有のサブセットで、配信されるファイルはCDNの運営者が代わりに設定します。ユーザーはCDNネットワークに参加すると、許可されたファイルをダウンロードして共有できます。ユーザーは、ファイル共有と同様のメリットを得ることができます。

このようなCDNは、外部との接続性は悪いが、LANの接続性は良いというオフィスでの使用に適しています。一人のユーザーがビデオをダウンロードし、それを他のユーザーと共有できます。誰もが外部ネットワーク経由で同じファイルを取得しようとしないので、転送がより速く完了します。

## WebRTCトポロジー

WebRTCは2つのエージェントを接続するためのプロトコルですが、開発者はどのようにして数百人を一度に接続しているのでしょうか？これにはいくつかの方法があり、それぞれに長所と短所があります。これらのソリューションは大きく分けて、「ピアツーピア」と「クライアント／サーバー」の2つのカテゴリーに分類されます。WebRTC の柔軟性により、その両方を実現できます。

### 1 対 1 

1 対 1 は WebRTC で使用する最初の接続形態です。2 つの WebRTC Agent を直接接続して、双方向のメディアやデータを送信できます。
接続は以下のようになります。

![One-to-One](/images/08-one-to-one.png "One-to-One")

### フルメッシュ
カンファレンスコールやマルチプレイヤーゲームを構築する場合は、フルメッシュが最適です。このトポロジーでは、各ユーザーが他のすべてのユーザーと直接接続を確立します。これにより、アプリケーションを構築できますが、いくつかのデメリットがあります。

フルメッシュトポロジーでは、各ユーザーが直接接続されます。そのため、通話相手ごとにビデオのエンコードやアップロードを行う必要があります。
各接続間のネットワーク状況は異なるため、同じ映像を再利用することはできません。また、このような環境では、エラー処理も難しくなります。完全な接続性が失われたのか、それとも1つのリモートピアとの接続性だけが失われたのかを慎重に検討する必要があります。

このような問題があるため、フルメッシュは少人数のグループに使用するのが最適です。それ以上の規模の場合は、クライアント/サーバー型のトポロジーが最適です。

![Full mesh](/images/08-full-mesh.png "Full mesh")

### ハイブリッドメッシュ

ハイブリッドメッシュは、フルメッシュの問題点を軽減することができるフルメッシュの代替手段です。ハイブリッドメッシュでは、すべてのユーザー間で接続を確立しません。ハイブリッドメッシュでは、すべてのユーザー間で接続するのではなく、ネットワーク内のピアを介してメディアを中継します。これにより、メディアの作成者は、メディアを配信するために多くの帯域を使用する必要がありません。

しかし、これにはいくつかのデメリットがあります。この設定では、メディアのオリジナル作成者は、自分のビデオが誰に送られているのか、そしてそれが正常に到着したのかを知ることができません。また、ハイブリッド・メッシュ・ネットワークでは、ホップごとにレイテンシーが増加してしまいます。

![Hybrid mesh](/images/08-hybrid-mesh.png "Hybrid mesh")

### 選択的フォワーディングユニット (Selective Forwarding Unit)

SFU(Selective Forwarding Unit)もフルメッシュの問題点を解決しますが、方法は全く異なります。SFUは、P2Pではなく、クライアント/サーバー型のトポロジーを実装しています。
各WebRTCピアはSFUに接続し、メディアをアップロードします。SFUはこのメディアを、接続された各クライアントに転送します。

SFUでは、各WebRTCエージェントがビデオをエンコードしてアップロードするのは一度だけです。すべての視聴者に配信する負担はSFUにあります。
SFUの接続はP2Pよりもはるかに簡単です。SFUはワールドルーティング可能なアドレスで動作させることができるので、クライアントの接続が非常に容易になります。
NATマッピングを気にする必要もありません。ただし、SFUがTCP経由で利用可能であることを確認する必要があります（ICE-TCPまたはTURN経由）。

シンプルなSFUの構築は、週末にでもできます。すべてのタイプのクライアントを処理できる優れたSFUを構築するには、終わりがありません。輻輳制御、エラー訂正、パフォーマンスのチューニングは終わりのない作業です。

![Selective Forwarding Unit](/images/08-sfu.png "Selective Forwarding Unit")

### MCU

MCU (Multi-point Conferencing Unit) は、SFU と同様のクライアント/サーバー型のトポロジーですが、出力ストリームを合成します。MCU (Multi-point Conferencing Unit)はSFUと同様のクライアント/サーバー型トポロジーですが、出力ストリームを合成します。

![Multi-point Conferencing Unit](/images/08-mcu.png "Multi-point Conferencing Unit")
