---
title: WritableStream.abort()
slug: Web/API/WritableStream/abort
l10n:
  sourceCommit: c575deb5f1775b532360c612a85b35a5ff9525d9
---

{{APIRef("Streams")}}

**`abort()`** は {{domxref("WritableStream")}} インターフェイスのメソッドで、ストリーミングを中止し、プロデューサーがストリームに正常に書き込むことができなくなり、キューに入れられた書き込みが破棄されてすぐにエラー状態に移行することを通知します。

## 構文

```js-nolint
abort(reason)
```

### 引数

- reason
  - : 人間が読むことのできる文字列で、中止した理由を提供します。

### 返値

{{jsxref("Promise")}} です。 `reason` 引数で指定された値で満たされます。

### 例外

- {{jsxref("TypeError")}}
  - : 中止しようとしているストリームは {{domxref("WritableStream")}} ではないか、ロックされています。

## 例

```js
const writableStream = new WritableStream(
  {
    write(chunk) {
      // ...
    },
    close() {
      // ...
    },
    abort(err) {
      // ...
    },
  },
  queuingStrategy,
);

// ...

// 必要に応じて、後でストリームを中止します
writableStream.abort();
```

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}
