---
title: "&#220;bersicht &#252;ber das Marshaling in C++"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "marshaling"
  - "marshalling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++-Unterstützungsbibliothek, Marshalling"
  - "Marshalling, Informationen über das Marshalling"
  - "Visual C++, Marshalling"
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;bersicht &#252;ber das Marshaling in C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im gemischten Modus müssen Sie die Daten zwischen systemeigenen und verwalteten Typen manchmal marshallen.  Mit [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)] wurde die Marshallingbibliothek eingeführt, mit der Sie Daten auf einfache Weise marshallen und konvertieren können.  
  
 Sie können die Marshallingbibliothek mit oder ohne eine [marshal\_context\-Klasse](../dotnet/marshal-context-class.md) verwenden.  Einige Konvertierungen erfordern einen Kontext.  Andere Konvertierungen können mithilfe der [marshal\_as](../dotnet/marshal-as.md)\-Funktion implementiert werden.  Die folgende Tabelle enthält eine Liste der aktuell unterstützten Konvertierungen und Informationen dazu, ob sie einen Kontext benötigen und welche Marschalldatei Sie hinzufügen müssen:  
  
|Von Typ|in Typ|Marschallmethode|Includedatei|  
|-------------|------------|----------------------|------------------|  
|System::String^|const char\*|marshal\_context|marshal.h|  
|const char\*|System::String^|marshal\_as|marshal.h|  
|char\*|System::String^|marshal\_as|marshal.h|  
|System::String^|const wchar\_t\*|marshal\_context|marshal.h|  
|const wchar\_t \*|System::String^|marshal\_as|marshal.h|  
|wchar\_t\*|System::String^|marshal\_as|marshal.h|  
|System::IntPtr|HANDLE|marshal\_as|marshal\_windows.h|  
|HANDLE|System::IntPtr|marshal\_as|marshal\_windows.h|  
|System::String^|BSTR|marshal\_context|marshal\_windows.h|  
|BSTR|System::String^|marshal\_as|marshal.h|  
|System::String^|bstr\_t|marshal\_as|marshal\_windows.h|  
|bstr\_t|System::String^|marshal\_as|marshal\_windows.h|  
|System::String^|std::string|marshal\_as|marshal\_cppstd.h|  
|std::string|System::String^|marshal\_as|marshal\_cppstd.h|  
|System::String^|std::wstring|marshal\_as|marshal\_cppstd.h|  
|std::wstring|System::String^|marshal\_as|marshal\_cppstd.h|  
|System::String^|CStringT\<char\>|marshal\_as|marshal\_atl.h|  
|CStringT\<char\>|System::String^|marshal\_as|marshal\_atl.h|  
|System::String^|CStringT\<wchar\_t\>|marshal\_as|marshal\_atl.h|  
|CStringT\<wchar\_t\>|System::String^|marshal\_as|marshal\_atl.h|  
|System::String^|CComBSTR|marshal\_as|marshal\_atl.h|  
|CComBSTR|System::String^|marshal\_as|marshal\_atl.h|  
  
 Marshalling erfordert nur einen Kontext, wenn Sie von verwalteten in systemeigene Datentypen marshallen und der systemeigene Typ, den Sie konvertieren, keinen Destruktor zur automatischen Bereinigung besitzt.  Der Marshallingkontext zerstört den zugeordneten systemeigenen Datentyp in seinem Destruktor.  Daher sind Konvertierungen, die einen Kontext erfordern, nur gültig, bis der Kontext gelöscht wird.  Um alle gemarshallten Werte zu speichern, müssen Sie die Werte in Ihre eigenen Variablen kopieren.  
  
> [!NOTE]
>  Wenn Sie `NULL` in die Zeichenfolge eingebettet haben, ist das Ergebnis des Marshallens der Zeichenfolge nicht garantiert.  Durch eine eingebettete `NULL` kann die Zeichenfolge abgeschnitten oder beibehalten werden.  
  
 Die Marshallingbibliotheksheader sind im Includeverzeichnis im Unterverzeichnis "msclr" gespeichert.  Dieses Beispiel zeigt, wie das Verzeichnis "msclr" einer Includeheaderdeklaration hinzugefügt wird:  
  
 `#include "msclr\marshal_cppstd.h"`  
  
 Die Marshallingbibliothek ist erweiterbar, sodass Sie eigene Marshallingtypen hinzufügen können.  Weitere Informationen zum Erweitern der Marshallingbibliothek finden Sie unter [Gewusst wie: Erweitern der Marshallingbibliothek](../dotnet/how-to-extend-the-marshaling-library.md).  
  
 In früheren Versionen konnten Sie Daten mithilfe eines [Plattformaufrufs](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md) marshallen.  Weitere Informationen über `PInvoke` finden Sie unter [Aufrufen systemeigener Funktionen aus verwaltetem Code](../dotnet/calling-native-functions-from-managed-code.md).  
  
## Siehe auch  
 [C\+\+\-Unterstützungsbibliothek](../dotnet/cpp-support-library.md)   
 [Gewusst wie: Erweitern der Marshallingbibliothek](../dotnet/how-to-extend-the-marshaling-library.md)