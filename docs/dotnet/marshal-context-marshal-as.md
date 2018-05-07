---
title: marshal_context::marshal_as | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_context::marshal_as
- marshal_context.marshal_as
- msclr.interop.marshal_context.marshal_as
- msclr::interop::marshal_context::marshal_as
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 24a1afee-51c0-497c-948c-f77fe43635c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 27f27b164d7a00e05e8d080a692f97b696776cbe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="marshalcontextmarshalas"></a>marshal_context::marshal_as
Führt das Marshalling für ein bestimmtes Datenobjekt zwischen einer verwalteten und systemeigenen Datentyp konvertieren.  
  
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
 Diese Funktion führt das Marshalling für ein bestimmtes Datenobjekt. Verwenden Sie diese Funktion nur für die Konvertierungen, die von der Tabelle im angegebenen [Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md).  
  
 Wenn Sie versuchen, ein Paar von Datentypen zu marshallen, die nicht unterstützt werden, `marshal_as` generiert einen Fehler [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) zum Zeitpunkt der Kompilierung. Weitere Informationen zu dem Fehler finden Sie in der zugehörigen Meldung. Der Fehler `C4996` kann auch bei anderen Problemen als veralteten Funktionen generiert werden. Zwei Bedingungen, die diesen Fehler zu generieren, werden bei dem Versuch, ein Paar von Datentypen zu marshallen, die nicht unterstützt werden und verwenden möchten `marshal_as` für eine Konvertierung, die einen Kontext benötigt.  
  
 Die Marshallingbibliothek besteht aus mehreren Headerdateien. Für jede Konvertierung ist nur eine Datei erforderlich, Sie können bei Bedarf jedoch zusätzliche Dateien für andere Konvertierungen einbinden. Die Tabelle in `Marshaling Overview in C++` gibt an, welche Marshalling-Datei für jede Konvertierung einbezogen werden sollen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel erstellt einen Kontext für das Marshalling von einem `System::String` zu einem `const char *` Variablentyp. Die konvertierten Daten werden nach der Zeile nicht gültig, mit dem den Kontext gelöscht.  
  
```  
// marshal_context_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   marshal_context^ context = gcnew marshal_context();  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = context->marshal_as<const char*>( message );  
   delete context;  
   return 0;  
}  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, oder \<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)   
 [marshal_context-Klasse](../dotnet/marshal-context-class.md)