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
ms.openlocfilehash: 6071cef3d5669fda86975bb0f27a2b9b87eeb011
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407269"
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

[override-Bezeichner](../cpp/override-specifier.md)<br/>
[Überschreibungsspezifizierer](../windows/override-specifiers-cpp-component-extensions.md)