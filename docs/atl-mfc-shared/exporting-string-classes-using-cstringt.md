---
title: Exportieren von CStringT mit Zeichenfolgenklassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7510b1f44f49d17211c71419f4dde5a6e6a78974
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="exporting-string-classes-using-cstringt"></a>CStringT mit Zeichenfolgenklassen exportieren
In der Vergangenheit MFC-Entwickler abgeleitet haben `CString` eigene Zeichenfolgenklassen spezialisiert werden kann. In Microsoft Visual C++ .NET (MFC 8.0) die [CString](../atl-mfc-shared/using-cstring.md) Klasse wurde ersetzt durch eine Vorlagenklasse, die aufgerufen [CStringT](../atl-mfc-shared/reference/cstringt-class.md). Diese Option angegeben mehrere Vorteile:  
  
-   Sie darf die MFC-Bibliothek `CString` -Klasse in ATL verwendet werden ohne zu verknüpfen, die in der größeren statischen MFC-Bibliothek oder DLL-Projekte.  
  
-   Mit dem neuen `CStringT` Vorlagenklasse, die Sie anpassen können `CString` Verhalten unter Verwendung der Vorlagenparameter, mit denen Zeichenmerkmale, ähnlich wie die Vorlagen in der C++-Standardbibliothek angegeben.  
  
-   Wenn Sie eine eigene Zeichenfolgenklasse aus einer DLL mithilfe exportieren `CStringT`, der Compiler automatisch auch exportiert die `CString` Basisklasse. Da `CString` selbst eine Vorlagenklasse, wird es möglicherweise instanziiert werden, indem der Compiler verwendet, es sei denn, dem Compiler bekannt ist, `CString` aus einer DLL importiert wird. Wenn Sie Projekte aus Visual C++ 6.0 auf Visual c++.NET migriert haben, Sie haben eventuell bereits Symbol Linkerfehler für ein mehrfach definiertes `CString` aufgrund des Konflikts, der die `CString` aus einer DLL und die lokal instanziierte Version importiert. Der richtige Weg zu diesem Zweck wird im folgenden beschrieben. Weitere Informationen zu diesem Problem finden Sie unter im Knowledge Base-Artikel "verknüpfen-Fehler beim Importieren von CString-abgeleitete Klassen" (Q309801) am [ http://support.microsoft.com/default.aspx ](http://support.microsoft.com/default.aspx).  
  
 Das folgende Szenario führt dazu, dass den Linker symbolfehler für multiply definierten Klassen zu erzeugen. Wird davon ausgegangen, dass Sie beim Exportieren in eine `CString`-Klasse (`CMyString`) aus einer MFC-Erweiterungs-DLL:  
  
 [!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]  
  
 Der Consumercode verwendet eine Kombination von `CString` und `CMyString`. "MyString.h" ist nicht in der vorkompilierte Header und einige Verwendung von enthalten `CString` verfügt nicht über `CMyString` sichtbar.  
  
 Angenommen, Sie verwenden die `CString` und `CMyString` Klassen in separaten Quelldateien Source1.cpp und Source2.cpp. In Source1.cpp, verwenden Sie `CMyString` und #include MyString.h. In Source2.cpp, verwenden Sie `CString`, nicht jedoch mit #include MyString.h. In diesem Fall wird der Linker zu beschweren `CStringT` mehrfach definiert wird. Ursache ist `CString` wird sowohl von der DLL, die exportiert importiert `CMyString`, und lokal instanziiert, indem der Compiler über die `CStringT` Vorlage.  
  
 Um dieses Problem zu beheben, führen Sie folgende Schritte aus:  
  
 Exportieren Sie `CStringA` und `CStringW` (und die erforderlichen Basisklassen) von MFC90. DLL. Projekte, die MFC verwendet immer die MFC-DLL exportiert `CStringA` und `CStringW`, wie in früheren MFC-Implementierungen.  
  
 Erstellen Sie dann einen exportierbaren abgeleiteten Klasse unter Verwendung der `CStringT` Vorlage als `CStringT_Exported` unterschreitet, beispielsweise:  
  
 [!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]  
  
 Ersetzen Sie im AfxStr.h, die vorherige `CString`, `CStringA`, und `CStringW` Typdefinitionen wie folgt:  
  
 [!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]  
  
 Es gibt mehrere Einschränkungen zu beachten:  
  
-   Sie sollten nicht exportieren `CStringT` selbst da dies nur ATL-Projekte verursacht So exportieren Sie ein spezieller `CStringT` Klasse.  
  
-   Mithilfe einer exportierbaren Klasse aus `CStringT` minimiert, dass erneut implementieren `CStringT` Funktionalität. Kein zusätzlicher Code ist beschränkt auf Konstruktoren, um die Weiterleitung der `CStringT` Basisklasse.  
  
-   `CString`, `CStringA`, und `CStringW` sollte nur markiert `__declspec(dllexport/dllimport)` gemeinsam genutzte beim Erstellen einer MFC-DLL. Wenn mit einer statischen MFC-Bibliothek zu verknüpfen, sollten Sie diese Klassen nicht als exportiert markieren; andernfalls, die interne Verwendung von `CString`, `CStringA`, und `CStringW` in Benutzer DLLs markieren `CString` als ebenfalls exportiert.  
  
## <a name="related-topics"></a>Verwandte Themen  
 [CStringT-Klasse](../atl-mfc-shared/reference/cstringt-class.md)  
  
## <a name="see-also"></a>Siehe auch  
 [CStringT verwenden](../atl-mfc-shared/using-cstringt.md)   
 [Verwenden von CString](../atl-mfc-shared/using-cstring.md)

