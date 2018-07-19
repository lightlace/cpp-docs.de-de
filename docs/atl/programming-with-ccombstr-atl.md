---
title: Programmieren mit CComBSTR (ATL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0cae1e2f05484aeccd76e987c2d63c41aec30f6
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848437"
---
# <a name="programming-with-ccombstr-atl"></a>Programmieren mit CComBSTR (ATL)
Der ATL-Klasse [CComBSTR](../atl/reference/ccombstr-class.md) bietet einen Wrapper für den BSTR-Datentyp. Während `CComBSTR` ist ein nützliches Werkzeug, es gibt mehrere Situationen mit Vorsicht.  
  
-   [Probleme bei der Konvertierung](#programmingwithccombstr_conversionissues)  
  
-   [Scope-Probleme](#programmingwithccombstr_scopeissues)  
  
-   [Explizites Freigeben der CComBSTR-Objekt](#programmingwithccombstr_explicitlyfreeing)  
  
-   [Verwenden von CComBSTR-Objekten in Schleifen](#programmingwithccombstr_usingloops)  
  
-   [Verlust von Arbeitsspeicherproblemen](#programmingwithccombstr_memoryleaks)  
  
##  <a name="programmingwithccombstr_conversionissues"></a> Probleme bei der Konvertierung  
 Obwohl mehrere `CComBSTR` Methoden werden automatisch ein Argument für ANSI in Unicode konvertiert, die Methoden immer Unicode-Formatzeichenfolgen zurück. Um die Ausgabezeichenfolge zurück zu ANSI zu konvertieren, verwenden Sie eine ATL-Konvertierung-Klasse. Weitere Informationen zu den ATL-konvertierungsklassen, finden Sie unter [ATL- und MFC-Zeichenfolgen-Konvertierungsmakros](reference/string-conversion-macros.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]  
  
 Wenn Sie so ändern Sie ein Zeichenfolgenliteral verwenden eine `CComBSTR` Objekt, das Breitzeichen-Zeichenfolgen verwenden. Dies reduziert unnötige Konvertierungen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]  
  
##  <a name="programmingwithccombstr_scopeissues"></a> Scope-Probleme  
 Wie bei der jede Klasse kaum `CComBSTR` gibt seine Ressourcen frei, wenn sie den Gültigkeitsbereich verlässt. Wenn eine Funktionsergebnis ist einen Zeiger auf die `CComBSTR` Zeichenfolge ist, dies kann Probleme verursachen, wie die Zeiger auf Speicher verweist, das bereits freigegeben wurde. In diesen Fällen verwenden die `Copy` Methode, wie unten dargestellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]  
  
##  <a name="programmingwithccombstr_explicitlyfreeing"></a> Explizites Freigeben der CComBSTR-Objekt  
 Es ist möglich, explizit freizugeben, die Zeichenfolge in die `CComBSTR` -Objekt, bevor das Objekt, den Gültigkeitsbereich verlässt. Wenn die Zeichenfolge freigegeben wird, die `CComBSTR` Objekt ist ungültig.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]  
  
##  <a name="programmingwithccombstr_usingloops"></a> Verwenden von CComBSTR-Objekten in Schleifen  
 Als die `CComBSTR` Klasse weist einen Puffer um bestimmte Vorgänge auszuführen, z. B. die `+=` Operator oder `Append` Methode, es wird nicht empfohlen, dass Sie Zeichenfolgen innerhalb einer engen Schleife ausführen. In diesen Situationen `CStringT` bietet eine bessere Leistung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]  
  
##  <a name="programmingwithccombstr_memoryleaks"></a> Verlust von Arbeitsspeicherproblemen  
 Übergeben Sie die Adresse des ein initialisiertes `CComBSTR` an eine Funktion als eine **[Out]** Parameter bewirkt, dass einen Speicherverlust.  
  
 Im folgenden Beispiel wird die Zeichenfolge, die für die Zeichenfolge zugeordneten `"Initialized"` geht verloren, wenn die Funktion `MyGoodFunction` ersetzt die Zeichenfolge.  
  
 [!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]  
  
 Um den Speicherverlust zu vermeiden, rufen Sie die `Empty` Methode für vorhandene `CComBSTR` Objekte vor der Übergabe der Adresse als eine **[Out]** Parameter.  
  
 Beachten Sie, dass der gleiche Code kein Verlust führen würde, wenn der Funktion-Parameter wurde **[in, out]**.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [CStringT-Klasse](../atl-mfc-shared/reference/cstringt-class.md)   
 [wstring](../standard-library/basic-string-class.md)   
 [Zeichenfolgenkonvertierungs-Makros](../atl/reference/string-conversion-macros.md)

