---
title: außer Kraft setzen (Komponentenerweiterungen für C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 708b69bc63e59d8ba6ba882d894d6f17b59d8237
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592368"
---
# <a name="override--c-component-extensions"></a>override (Komponentenerweiterungen für C++)

Die **überschreiben** kontextbezogenes Schlüsselwort Gibt an, dass ein Member eines Typs eine Basisklasse oder einen Basisschnittstellenmember überschreibt.

## <a name="remarks"></a>Hinweise

Die **überschreiben** Schlüsselwort ist gültig, beim Kompilieren für systemeigene Ziele (standardmäßige Compileroption), Windows-Runtime-Ziele (`/ZW` -Compileroption), oder der common Language Runtime-Ziele (`/clr` -Compileroption).

Weitere Informationen zu überschreibungsspezifizierern finden Sie unter [Überschreibungsspezifizierer](../cpp/override-specifier.md) und [Überschreibungsspezifizierer und Native Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

Weitere Informationen zu kontextbezogenen Schlüsselwörtern finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).

## <a name="examples"></a>Beispiele

Das folgende Codebeispiel zeigt, dass **überschreiben** kann auch in nativen Kompilierungen verwendet werden.

```cpp
// override_keyword_1.cpp
// compile with: /c
struct I1 {
   virtual void f();
};

struct X : public I1 {
   virtual void f() override {}
};
```

### <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt, dass **überschreiben** in Windows-Runtime-Kompilierungen verwendet werden kann.

```cpp 
// override_keyword_2.cpp
// compile with: /ZW /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

### <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt, dass **überschreiben** in common Language Runtime-Kompilierungen verwendet werden kann.

```cpp
// override_keyword_3.cpp
// compile with: /clr /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

## <a name="see-also"></a>Siehe auch

[override-Bezeichner](../cpp/override-specifier.md)  
[Überschreibungsspezifizierer](../windows/override-specifiers-cpp-component-extensions.md)