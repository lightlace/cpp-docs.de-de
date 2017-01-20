---
title: "Exporting String Classes Using CStringT"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringT class, exporting strings"
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
caps.latest.revision: 15
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Exporting String Classes Using CStringT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der Vergangenheit haben MFC\-Entwickler von `CString` abgeleitet, eigene Zeichenfolgenklassen zu spezialisieren.  In Microsoft Visual C\+\+ .NET MFC \(8.0\), wurde die [CString](../atl-mfc-shared/using-cstring.md)\-Klasse durch eine Vorlagenklasse ersetzt, die [CStringT](../atl-mfc-shared/reference/cstringt-class.md) aufgerufen wurde.  Dies kann mehrere Vorteile:  
  
-   Es konnten die in den ATL\-Projekten verwendet werden `CString` MFC, Klasse, ohne in der größeren statischen MFC\-Bibliothek oder im DLL zu verknüpfen.  
  
-   Mit der neuen `CStringT` Vorlagenklasse können Sie `CString` Verhalten mithilfe von Vorlagenparameter anpassen, die Zeichenmerkmale angeben, ähnlich den Vorlagen in der Standardvorlagenbibliothek \(STL\).  
  
-   Wenn Sie eine eigene Zeichenfolgenklasse aus einer DLL mithilfe von `CStringT` exportieren, exportiert der Compiler auch automatisch die `CString` Basisklasse.  Da `CString` selbst eine Vorlagenklasse wurde, wird sie vom Compiler instanziiert werden, wenn sie verwendet wird, es sei denn, der Compiler erwähnt, dass `CString` aus einer DLL importiert wird.  Wenn Sie Projekte von Visual C\+\+ 6.0 auf Visual C\+\+ .NET migriert haben, sehen Sie möglicherweise Linkersymbolfehler für mehrfach definiertes `CString` aufgrund des Konflikts `CString`, das aus einer DLL und der lokal instanziierten Version importiert wird.  Die richtige Methode, hierzu ist unten beschrieben.  Weitere Informationen über dieses Problem, finden Sie im Knowledge Base\-Artikel, "Fehler Verknüpfen von, wenn Sie CString\-abgeleitete Klassen" \(Q309801\) auf der MSDN Library\-CD\-ROM oder an [http:\/\/support.microsoft.com\/default.aspx](http://support.microsoft.com/default.aspx) importieren.  
  
 Im folgenden Szenario wird der Linker, Symbolfehler für mehrfach definierte Klassen zu erzeugen.  Angenommen, Sie `CString` von abgeleitete Klasse \(`CMyString`\) einer MFC\-Erweiterungs\-DLL exportieren:  
  
 [!CODE [NVC_MFC_DLL#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_DLL#6)]  
  
 Der Consumercode verwendet eine Kombination von `CString` und von `CMyString`. "  MyString.h" wird nicht in vorkompilierter Header enthalten, und einige Verwendung von `CString` hat nicht sichtbar `CMyString`.  
  
 Angenommen, Sie die `CString` und `CMyString`\-Klassen in separaten Quelldateien, Source1.cpp und Source2.cpp verwenden.  In Source1.cpp verwenden Sie `CMyString` und \#include MyString.h.  In Source2.cpp verwenden Sie `CString`, aber dies jedoch nicht \#include MyString.h.  In diesem Fall beschwert sich der Linker über `CStringT`, das mehrfach definiert ist.  Dies wird durch `CString` Importieren aus der DLL, das `CMyString` exportiert, und vom Compiler durch die `CStringT` Vorlage lokal instanziiert verursacht.  
  
 Um dieses Problem zu beheben, stellen Sie Folgendes:  
  
 Exportieren Sie `CStringA` und `CStringW` \(und die erforderlichen Basisklassen\) von MFC90.DLL.  Projekte, die MFC enthalten, verwenden immer MFC\-DLL exportierte `CStringA` und `CStringW`, wie in vorherigen MFC\-Implementierungen.  
  
 Erstellen Sie dann eine exportierbare abgeleitete Klasse mithilfe der `CStringT` Vorlage, während `CStringT_Exported` unten ist, beispielsweise:  
  
 [!CODE [NVC_MFC_DLL#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_DLL#7)]  
  
 In AfxStr.h ersetzen Sie vorherige `CString`, `CStringA` und `CStringW`\-Typdefinitionen, wie folgt:  
  
 [!CODE [NVC_MFC_DLL#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_DLL#8)]  
  
 Es gibt einige Vorsicht:  
  
-   Sie sollten `CStringT` selbst nicht exportieren, da dies nur für ATL Projekte verursacht, eine spezielle `CStringT`\-Klasse zu exportieren.  
  
-   Verwenden einer exportfähigen abgeleitete Klasse von `CStringT` minimiert das `CStringT`\-Funktionalität nicht erneut implementieren.  Code wird zum Weiterleiten von Konstruktoren zur `CStringT` Basisklasse beschränkt.  
  
-   `CString`, `CStringA` und `CStringW` sollten als `__declspec(dllexport/dllimport)` nur sein, wenn Sie mit einer MFC\-gemeinsamengenutztem DLL erstellen.  Beim Verknüpfen mit einer statischen MFC\-Bibliothek, sollten Sie diese Klassen markieren nicht, wie exportiert; andernfalls markiert interne Verwendung von `CString`, von `CStringA` und von `CStringW` innerhalb des Benutzers DLL `CString`, wie auch exportiert.  
  
## Verwandte Themen  
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)  
  
## Siehe auch  
 [Using CStringT](../atl-mfc-shared/using-cstringt.md)   
 [Using CString](../atl-mfc-shared/using-cstring.md)