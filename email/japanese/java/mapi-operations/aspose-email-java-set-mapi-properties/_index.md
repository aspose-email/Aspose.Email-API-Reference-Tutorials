---
"date": "2025-05-29"
"description": "Aspose.Email for Java を使用して、MAPI メッセージ内の複数のプロパティを効率的に管理する方法を学びます。このガイドでは、float、double、long などの型の設定について説明します。"
"title": "Aspose.Email を使って Java で複数の MAPI プロパティを設定する方法 - 総合ガイド"
"url": "/ja/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email を使用して Java で複数の MAPI プロパティを設定する: 包括的なガイド

## 導入

MAPIメッセージプロパティを効果的に管理することは、Javaアプリケーションの拡張に不可欠です。Aspose.Email for Javaを使用すると、float、double、long、short、boolean、カスタムプロパティなど、複数のプロパティをシームレスに設定できます。このガイドでは、これを実現するための様々な方法について解説します。

**学習内容:**
- Aspose.Email Java を使用して MAPI メッセージに複数のプロパティを設定する
- さまざまな不動産の種類とその用途を理解する
- 実装のための実用的なコード例

まず前提条件について説明します。

## 前提条件

この手順を実行するには、次のものを用意してください。
- **Java 開発キット (JDK):** JDK 8 以降がインストールされています。
- **Aspose.Email ライブラリ:** バージョン25.4が推奨されます。
- **Maven のセットアップ:** 依存関係を管理するには、IDE で Maven を設定する必要があります。

### 必要なライブラリ

Aspose.Emailを依存関係として含める `pom.xml`：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ライセンス取得
- **無料トライアル:** まずは無料トライアルで機能をご確認ください。
- **一時ライセンス:** 制限なしで拡張テストを取得します。
- **購入：** ニーズに合う場合は購入を検討してください。

## Aspose.Email for Java の設定

開発環境で Aspose.Email が正しく構成されていることを確認します。
1. **インポート依存関係:** Maven の依存関係を解決します。
2. **ライセンスを設定:**
   - ライセンスファイルをダウンロードするには [アポーズ](https://purchase。aspose.com/buy).
   - 以下を使用して適用します。
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

セットアップが完了したら、さまざまなプロパティを設定する方法を調べてみましょう。

## 実装ガイド

### 複数のフロートプロパティの設定

float プロパティを設定すると、数値データを効率的に保存できます。

#### 概要
この機能は、Aspose.Email for Java を使用して複数の float 値を MAPI メッセージ プロパティとして追加する方法を示します。

#### 手順
1. **メッセージの作成と初期化**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **リストに浮動小数点値を追加する**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **一意の識別子を使用してプロパティを設定する**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*説明：* プロパティタグ `0x23901004` この float プロパティ セットを識別します。

### 複数のdoubleプロパティの設定

Double プロパティは高精度の浮動小数点数を格納します。

#### 概要
このセクションでは、複数の double 値を MAPI メッセージ プロパティとして保存する方法を説明します。

#### 手順
1. **メッセージを初期化する**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **倍精度値を入力する**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **プロパティタグに割り当てる**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### 複数のAPPTIMEプロパティの設定

APPTIME プロパティは時間の長さを効率的に保存します。

#### 概要
この機能は、時間表現に倍精度数値を使用する方法を示しています。

#### 手順
1. **メッセージオブジェクトを作成する**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **時間値を追加する**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **プロパティを設定する**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### 複数の長いプロパティの設定

Long プロパティは大きな整数に最適です。

#### 概要
この機能は、メッセージ内に複数の長整数値を設定することに重点を置いています。

#### 手順
1. **MAPIメッセージの初期化**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **長い値を追加する**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **プロパティタグの定義**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### 複数のショートプロパティの設定

ショートプロパティは小さな整数データを効率的に保存します。

#### 概要
このガイドでは、短い整数をメッセージ プロパティとして設定する方法を説明します。

#### 手順
1. **メッセージを初期化する**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **短い値を追加する**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **プロパティタグの割り当て**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### 複数のブールプロパティの設定

ブール型プロパティは、真偽の状態を格納します。

#### 概要
メッセージに複数のブール値を設定する方法を学びます。

#### 手順
1. **メッセージオブジェクトを作成する**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **ブール値を追加する**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **識別子を使用してプロパティを設定する**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Nullプロパティの設定

プロパティを明示的に null に設定すると便利な場合があります。

#### 概要
このセクションでは、プロパティに null 値を割り当てる方法を説明します。

#### 手順
1. **メッセージを初期化する**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Nullプロパティの割り当て**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### カスタム ID と UUID を使用して名前付き Long プロパティを設定する

複雑なシナリオの場合は、名前付きプロパティを設定します。

#### 概要
この機能は、カスタム識別子と UUID を使用して長いプロパティを設定する方法を示します。

#### 手順
1. **メッセージを初期化する**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **長い値を追加する**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **プロパティの作成とマッピング**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### 名前付きカスタムプロパティの設定

カスタム プロパティには、識別しやすいように名前を付けることができます。

#### 概要
このガイドでは、カスタム名付きプロパティの設定方法を説明します。

#### 手順
1. **メッセージオブジェクトの初期化**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **カスタムプロパティを定義する**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### プロパティの設定と検証

プロパティが正しく設定されていることを確認することが重要です。

#### 概要
このセクションでは、MAPI メッセージの複数のプロパティの設定と検証について説明します。

#### 手順
1. **プロパティの設定**
   プロパティを設定するには、前の例に従ってください。
2. **プロパティの検証**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## 結論

このガイドでは、Aspose.Email for Java を使用して MAPI メッセージ内の複数のプロパティを管理するための包括的なアプローチを紹介しました。これらの手順に従うことで、アプリケーション内でさまざまなデータ型を効率的に保存および管理できます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}