---
title: marshal_as
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
ms.openlocfilehash: 2294d8fe94a32f281332c963b21a542366ae3207
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386082"
---
# <a name="marshalas"></a>marshal_as

Bei dieser Methode werden Daten zwischen systemeigenen und verwalteten Umgebungen konvertiert.

## <a name="syntax"></a>Syntax

```
To_Type marshal_as<To_Type>(
   From_Type input
);
```

#### <a name="parameters"></a>Parameter

*input*<br/>
[in] Der Wert, der zum Marshallen soll eine `To_Type` Variable.

## <a name="return-value"></a>Rückgabewert

Eine Variable vom Typ `To_Type`, bei dem es sich um den konvertierten Wert von `input` handelt.

## <a name="remarks"></a>Hinweise

Diese Methode ist eine vereinfachte Möglichkeit zum Konvertieren von Daten zwischen systemeigenen und verwalteten Typen. Um zu bestimmen, welche Datentypen unterstützt werden, finden Sie unter [Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md). Einige Datenkonvertierungen erfordern einen Kontext. Sie können diese Datentypen konvertieren, indem Sie mit der [Marshal_context-Klasse](../dotnet/marshal-context-class.md).

Wenn Sie versuchen, ein Paar von Datentypen zu marshallen, die nicht unterstützt werden, `marshal_as` generiert einen Fehler [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) zum Zeitpunkt der Kompilierung. Weitere Informationen zu dem Fehler finden Sie in der zugehörigen Meldung. Der Fehler `C4996` kann auch bei anderen Problemen als veralteten Funktionen generiert werden. Dazu zählt beispielsweise der Versuch, ein Paar von Datentypen zu marshallen, die nicht unterstützt werden.

Die Marshallingbibliothek besteht aus mehreren Headerdateien. Für jede Konvertierung ist nur eine Datei erforderlich, Sie können bei Bedarf jedoch zusätzliche Dateien für andere Konvertierungen einbinden. Informationen darüber, welche Konvertierungen welchen Dateien zugeordnet sind, finden Sie in der Tabelle in `Marshaling Overview`. Unabhängig vom Typ der durchzuführenden Konvertierung ist die Namespaceanforderung immer gültig.

## <a name="example"></a>Beispiel

In diesem Beispiel erfolgt das Marshalling von einem `const char*`- zu einem `System::String`-Variablentyp.

```
// marshal_as_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   const char* message = "Test String to Marshal";
   String^ result;
   result = marshal_as<String^>( message );
   return 0;
}
```

## <a name="requirements"></a>Anforderungen

**Headerdatei:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, oder \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>Siehe auch

[Übersicht über das Marshalling in C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_context-Klasse](../dotnet/marshal-context-class.md)
