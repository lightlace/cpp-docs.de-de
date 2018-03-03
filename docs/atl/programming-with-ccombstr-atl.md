---
title: Programmieren mit CComBSTR (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8f496dd73c2d15f8f78ddbdc205f31a8520c674
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="programming-with-ccombstr-atl"></a>Programmieren mit CComBSTR (ATL)
Die ATL-Klasse [CComBSTR](../atl/reference/ccombstr-class.md) stellt einen Wrapper um die `BSTR` -Datentyp. Während `CComBSTR` ist ein nützliches Tool, es gibt mehrere Situationen mit Vorsicht.  
  
-   [Konvertierungsprobleme](#programmingwithccombstr_conversionissues)  
  
-   [Bereichs-Probleme](#programmingwithccombstr_scopeissues)  
  
-   [CComBSTR-Objekt freigeben explizit](#programmingwithccombstr_explicitlyfreeing)  
  
-   [Verwenden von CComBSTR-Objekten in Schleifen](#programmingwithccombstr_usingloops)  
  
-   [Verlust von Arbeitsspeicherproblemen](#programmingwithccombstr_memoryleaks)  
  
##  <a name="programmingwithccombstr_conversionissues"></a>Konvertierungsprobleme  
 Obwohl mehrere `CComBSTR` Methoden werden automatisch ein Zeichenfolgenargument ANSI in Unicode konvertiert, die Methoden immer Unicode-Formatzeichenfolgen zurück. Um die Ausgabezeichenfolge wieder in ANSI zu konvertieren, verwenden Sie eine ATL-Konvertierung-Klasse. Weitere Informationen zu den ATL-konvertierungsklassen, finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](reference/string-conversion-macros.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]  
  
 Wenn Sie ein Zeichenfolgenliteral verwenden, so ändern Sie eine `CComBSTR` Objekt, das Breitzeichen-Zeichenfolgen verwenden. Dies reduziert die unnötige Konvertierung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]  
  
##  <a name="programmingwithccombstr_scopeissues"></a>Bereichs-Probleme  
 Wie bei einer gut konzipierte Klasse `CComBSTR` wird seine Ressourcen freizugeben, wenn sie den Gültigkeitsbereich verlässt. Wenn eine Funktion zurückgegeben wird einen Zeiger auf die `CComBSTR` Zeichenfolge, dies kann Probleme verursachen, wie die Zeiger auf Speicher verweist, das bereits freigegeben wurde. In diesen Fällen verwenden die **Kopie** Methode, wie unten dargestellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]  
  
##  <a name="programmingwithccombstr_explicitlyfreeing"></a>CComBSTR-Objekt freigeben explizit  
 Es ist möglich, eine Zeichenfolge, die explizit freigeben der `CComBSTR` -Objekt, bevor das Objekt außerhalb des Bereichs befindet. Wenn die Zeichenfolge freigegeben wird, die `CComBSTR` Objekt ist ungültig.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]  
  
##  <a name="programmingwithccombstr_usingloops"></a>Verwenden von CComBSTR-Objekten in Schleifen  
 Als die `CComBSTR` Klasse reserviert einen Puffer, um bestimmte Vorgänge ausführen, wie etwa die `+=` Operator oder **Append** Methode nicht empfohlen, dass Sie Zeichenfolgen in einer engen Schleife ausführen. In diesen Situationen `CStringT` bietet eine bessere Leistung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]  
  
##  <a name="programmingwithccombstr_memoryleaks"></a>Verlust von Arbeitsspeicherproblemen  
 Übergeben die Adresse des eine initialisierte `CComBSTR` an eine Funktion als ein **[Out]** Parameter bewirkt, dass einen Speicherverlust.  
  
 Im folgenden Beispiel wird die Zeichenfolge für die Zeichenfolge zugeordnet `"Initialized"` wurde abgegriffen, wenn die Funktion `MyGoodFunction` ersetzt die Zeichenfolge.  
  
 [!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]  
  
 Um den Verlust zu vermeiden, rufen die **leere** Methode auf vorhandenen `CComBSTR` Objekte vor Übergabe der Adresse als eine **[Out]** Parameter.  
  
 Beachten Sie, dass der gleiche Code kein Speicherverlust führen würde, wenn die Funktion Parameter wurde **[in, out]**.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [CStringT-Klasse](../atl-mfc-shared/reference/cstringt-class.md)   
 [wstring](../standard-library/basic-string-class.md)   
 [Zeichenfolgenkonvertierungs-Makros](../atl/reference/string-conversion-macros.md)

