---
title: Marshal_as | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
dev_langs:
- C++
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ebca4a94fa48feb4ff5fb897293303a395ac4eb8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133778"
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
 [in] `input`  
 Der Wert, der zu einer `To_Type`-Variable gemarshallt werden soll.  
  
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
 [Übersicht über das Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_context-Klasse](../dotnet/marshal-context-class.md)