---
title: "marshal_context::marshal_as | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_context::marshal_as"
  - "marshal_context.marshal_as"
  - "msclr.interop.marshal_context.marshal_as"
  - "msclr::interop::marshal_context::marshal_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context-Klasse [C++], Operationen"
ms.assetid: 24a1afee-51c0-497c-948c-f77fe43635c8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# marshal_context::marshal_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Führt das Marshalling für ein bestimmtes Datenobjekt aus, um es zwischen einem verwalteten und systemeigenen Datentyp konvertiert.  
  
## Syntax  
  
```  
To_Type marshal_as<To_Type>(  
   From_Type input   
);  
```  
  
#### Parameter  
 \[in\] `input`  
 Der Wert, der zu einer `To_Type`\-Variable gemarshallt werden soll.  
  
## Rückgabewert  
 Eine Variable vom Typ `To_Type`, bei dem es sich um den konvertierten Wert von `input` handelt.  
  
## Hinweise  
 Diese Funktion übergibt das Marshalling für ein bestimmtes Datenobjekt aus.  Verwenden Sie dieses Feature nur mit den Konvertierungen, die von der Tabelle in [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md) angegeben werden.  
  
 Wenn Sie versuchen, ein Paar nicht unterstützte Datentypen zu marshallen, generiert `marshal_as` beim Kompilieren den Fehler [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).  Weitere Informationen zu dem Fehler finden Sie in der zugehörigen Meldung.  Der Fehler `C4996` kann auch bei anderen Problemen als veralteten Funktionen generiert werden.  Zwei Bedingungen, die diesen Fehler verursachen, versuchen, ein Paar Datentypen zu marshallen, die nicht unterstützt wurden und versuchen, `marshal_as` für eine Umwandlung zu verwenden, die einen Kontext erfordert.  
  
 Die Marshallingbibliothek besteht aus mehreren Headerdateien.  Für jede Konvertierung ist nur eine Datei erforderlich, Sie können bei Bedarf jedoch zusätzliche Dateien für andere Konvertierungen einbinden.  Die Tabelle in `Marshaling Overview in C++` gibt an, die für jede Marshallingdatei Konvertierung eingeschlossen werden soll.  
  
## Beispiel  
 Dieses Beispiel erstellt einen Kontext für das Marshalling von `System::String` zu einem `const char *`\-Variablentyp.  Die konvertierten Daten sind nicht nach der Zeile, die den Kontext gültig löscht.  
  
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
  
## Anforderungen  
 **Headerdatei:** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\> oder \<msclr\\marshal\_atl.h\>  
  
 **Namespace:** msclr::interop  
  
## Siehe auch  
 [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)   
 [marshal\_context\-Klasse](../dotnet/marshal-context-class.md)