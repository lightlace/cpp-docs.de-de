---
title: make_public-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
ms.openlocfilehash: d12fab685e0088993cb43073c3603bda12edd2f3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218822"
---
# <a name="make_public-pragma"></a>make_public-Pragma

Gibt an, dass für einen systemeigenen Typ der öffentliche Assemblyzugriff gewährt wird.

## <a name="syntax"></a>Syntax

> **#pragma make_public (** *Typ* **)**

### <a name="parameters"></a>Parameter

*type*\
Der Name des Typs, für den die öffentliche Assembly zugänglich sein soll.

## <a name="remarks"></a>Hinweise

**make_public** ist nützlich für den Fall, dass der Native Typ, auf den Sie verweisen möchten, aus einer Header Datei stammt, die Sie nicht ändern können. Wenn Sie den systemeigenen Typ in der Signatur einer öffentlichen Funktion in einem Typ mit Sichtbarkeit öffentlicher Assemblys verwenden möchten, muss der systemeigene Typ auch den Zugriff auf die öffentliche Assembly aufweisen, oder der Compiler gibt eine Warnung aus.

**make_public** muss im globalen Gültigkeitsbereich angegeben werden. Sie ist nur von dem Zeitpunkt aus, an dem Sie deklariert wurde, bis zum Ende der Quell Code Datei wirksam.

Der Native Typ kann implizit oder explizit privat sein. Weitere Informationen finden Sie unter [Typsichtbarkeit](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility).

## <a name="examples"></a>Beispiele

Das folgende Beispiel ist der Inhalt einer Header Datei, die die Definitionen für zwei Native Strukturen enthält.

```cpp
// make_public_pragma.h
struct Native_Struct_1 { int i; };
struct Native_Struct_2 { int i; };
```

Im folgenden Codebeispiel wird die Header Datei verwendet. Es wird gezeigt, dass der Compiler eine Warnung generiert, wenn Sie versuchen, die nativen Strukturen in der Signatur der öffentlichen Funktion in einem öffentlichen verwalteten Typ zu verwenden, es sei denn, Sie markieren die systemeigenen Strukturen explizit mithilfe von **make_public**als öffentlich.

```cpp
// make_public_pragma.cpp
// compile with: /c /clr /W1
#pragma warning (default : 4692)
#include "make_public_pragma.h"
#pragma make_public(Native_Struct_1)

public ref struct A {
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692
};
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
