---
title: "Übersicht über das Marshaling in C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
dev_langs: C++
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 384c8bac652e16a4f66a82ee7e4dbb5cc92fd32b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="overview-of-marshaling-in-c"></a>Übersicht über das Marshalling in C++
Im gemischten Modus müssen Sie die Daten zwischen nativen und verwalteten Typen manchmal marshallen. Mit [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)] wurde die Marshallingbibliothek eingeführt, mit der Sie Daten auf einfache Weise marshallen und konvertieren können.  
  
 Sie können die Marshallingbibliothek verwenden, mit oder ohne ein [Marshal_context-Klasse](../dotnet/marshal-context-class.md). Einige Konvertierungen erfordern einen Kontext. Andere Konvertierungen können implementiert werden, mithilfe der [Marshal_as](../dotnet/marshal-as.md) Funktion. Die folgende Tabelle enthält eine Liste der aktuell unterstützten Konvertierungen und Informationen dazu, ob sie einen Kontext benötigen und welche Marschalldatei Sie hinzufügen müssen:  
  
|Von Typ|in Typ|Marschallmethode|Includedatei|  
|---------------|-------------|--------------------|------------------|  
|System::String^|const char*|marshal_context|marshal.h|  
|const char*|System::String^|marshal_as|marshal.h|  
|char*|System::String^|marshal_as|marshal.h|  
|System::String^|const wchar_t*|marshal_context|marshal.h|  
|const wchar_t *|System::String^|marshal_as|marshal.h|  
|wchar_t*|System::String^|marshal_as|marshal.h|  
|System::IntPtr|HANDLE|marshal_as|marshal_windows.h|  
|HANDLE|System::IntPtr|marshal_as|marshal_windows.h|  
|System::String^|BSTR|marshal_context|marshal_windows.h|  
|BSTR|System::String^|marshal_as|marshal.h|  
|System::String^|bstr_t|marshal_as|marshal_windows.h|  
|bstr_t|System::String^|marshal_as|marshal_windows.h|  
|System::String^|std::string|marshal_as|marshal_cppstd.h|  
|std::string|System::String^|marshal_as|marshal_cppstd.h|  
|System::String^|std::wstring|marshal_as|marshal_cppstd.h|  
|std::wstring|System::String^|marshal_as|marshal_cppstd.h|  
|System::String^|CStringT\<Char >|marshal_as|marshal_atl.h|  
|CStringT\<Char >|System::String^|marshal_as|marshal_atl.h|  
|System::String^|CStringT<wchar_t>|marshal_as|marshal_atl.h|  
|CStringT<wchar_t>|System::String^|marshal_as|marshal_atl.h|  
|System::String^|CComBSTR|marshal_as|marshal_atl.h|  
|CComBSTR|System::String^|marshal_as|marshal_atl.h|  
  
 Marshalling erfordert nur einen Kontext, wenn Sie von verwalteten in systemeigene Datentypen marshallen und der systemeigene Typ, den Sie konvertieren, keinen Destruktor zur automatischen Bereinigung besitzt. Der Marshallingkontext zerstört den zugeordneten systemeigenen Datentyp in seinem Destruktor. Daher sind Konvertierungen, die einen Kontext erfordern, nur gültig, bis der Kontext gelöscht wird. Um alle gemarshallten Werte zu speichern, müssen Sie die Werte in Ihre eigenen Variablen kopieren.  
  
> [!NOTE]
>  Wenn Sie `NULL` in die Zeichenfolge eingebettet haben, ist das Ergebnis des Marshallens der Zeichenfolge nicht garantiert. Durch eine eingebettete `NULL` kann die Zeichenfolge abgeschnitten oder beibehalten werden.  
  
 Die Marshallingbibliotheksheader sind im Includeverzeichnis im Unterverzeichnis "msclr" gespeichert. Dieses Beispiel zeigt, wie das Verzeichnis "msclr" einer Includeheaderdeklaration hinzugefügt wird:  
  
 `#include "msclr\marshal_cppstd.h"`  
  
 Die Marshallingbibliothek ist erweiterbar, sodass Sie eigene Marshallingtypen hinzufügen können. Weitere Informationen zum Erweitern der Marshallingbibliothek finden Sie unter [wie: Erweitern der Marshallingbibliothek](../dotnet/how-to-extend-the-marshaling-library.md).  
  
 In früheren Versionen konnten Sie Daten marshallen, indem [Plattformaufruf](/dotnet/framework/interop/consuming-unmanaged-dll-functions). Weitere Informationen zu `PInvoke`, finden Sie unter [Aufrufen systemeigener Funktionen aus verwaltetem Code](../dotnet/calling-native-functions-from-managed-code.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Unterstützungsbibliothek](../dotnet/cpp-support-library.md)   
 [Vorgehensweise: Erweitern der Marshallingbibliothek](../dotnet/how-to-extend-the-marshaling-library.md)