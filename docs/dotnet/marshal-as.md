---
title: "marshal_as | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_as"
  - "msclr.interop.marshal_as"
  - "msclr::interop::marshal_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_as-Vorlage [C++]"
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# marshal_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei dieser Methode werden Daten zwischen systemeigenen und verwalteten Umgebungen konvertiert.  
  
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
 Diese Methode ist eine vereinfachte Möglichkeit zum Konvertieren von Daten zwischen systemeigenen und verwalteten Typen.  Informationen zu den unterstützten Datentypen finden Sie unter [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md).  Einige Datenkonvertierungen erfordern einen Kontext.  Sie können diese Datentypen mithilfe der [marshal\_context\-Klasse](../dotnet/marshal-context-class.md) konvertieren.  
  
 Wenn Sie versuchen, ein Paar nicht unterstützte Datentypen zu marshallen, generiert `marshal_as` beim Kompilieren den Fehler [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).  Weitere Informationen zu dem Fehler finden Sie in der zugehörigen Meldung.  Der Fehler `C4996` kann auch bei anderen Problemen als veralteten Funktionen generiert werden.  Dazu zählt beispielsweise der Versuch, ein Paar von Datentypen zu marshallen, die nicht unterstützt werden.  
  
 Die Marshallingbibliothek besteht aus mehreren Headerdateien.  Für jede Konvertierung ist nur eine Datei erforderlich, Sie können bei Bedarf jedoch zusätzliche Dateien für andere Konvertierungen einbinden.  Informationen darüber, welche Konvertierungen welchen Dateien zugeordnet sind, finden Sie in der Tabelle in `Marshaling Overview`.  Unabhängig vom Typ der durchzuführenden Konvertierung ist die Namespaceanforderung immer gültig.  
  
## Beispiel  
 In diesem Beispiel erfolgt das Marshalling von einem `const char*`\- zu einem `System::String`\-Variablentyp.  
  
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
  
## Anforderungen  
 **Headerdatei:** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\> oder \<msclr\\marshal\_atl.h\>  
  
 **Namespace:** msclr::interop  
  
## Siehe auch  
 [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_context\-Klasse](../dotnet/marshal-context-class.md)