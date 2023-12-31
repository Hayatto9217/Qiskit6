# Qiskit6
Qiskit Terra の中核コンポーネントはトランスパイラーで、モジュール性と拡張性のために設計されています。目的は新しい回路の変換(トランスパイラー パス と呼んでいます) を簡単に書けるようにし、他の既存のパスと組み合わせられるようにすることです。これらのパスを連鎖させ、どの順番で適用するかは、最終的な結果に大きな影響を与えます。このパイプラインは パスマネージャー により決定されます。パスマネージャーは、パスをスケジューリングし、共有スペースによるパス間の相互通信を行えるようにしています。このようにトランスパイラーは、量子回路の積極的な最適化の研究のために、ドアを開放しています。

このノートブックでは、ビルドインされたパスを調べ、パスマネージャーの利用法を確認し、簡単なトランスパイラーパスを開発します。そのために、最初に有向非巡回グラフ（Directed Acyclic Graph、DAG）の形で、Qiskitにおける量子回路の内部表現を紹介します。次に、入力回路を接続性の制限された量子デバイスと互換性を持つように変換する、単純な swap mapper パスを示します。

始める前に: DAGプロットルーチンの pydot ライブラリと graphviz ライブラリをインストールする必要があります。 Anaconda Python を使用している場合は、conda コマンドを使用して両方をインストールできます。 システムのネイティブ Python インタプリタを使用する場合は、pip コマンドを使用して pydot をインストールし、システムのネイティブ パッケージ マネージャー (例．yum, apt, dnf, brew など) を使用して graphviz をインストールします。


# https://qiskit.org/documentation/locale/ja_JP/tutorials/circuits_advanced/04_transpiler_passes_and_passmanager.html
