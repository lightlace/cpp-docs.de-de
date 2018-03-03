---
title: "CString-Argumentenübergabe | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], as function input/output
- argument passing [C++]
- arguments [C++], passing
- functions [C++], strings as input/output
- argument passing [C++], C strings
- passing arguments, C strings
- CString objects, passing arguments
- string arguments
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d33c8cc46ada41f851c90aaae0cabfadb1466d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cstring-argument-passing"></a>CString-Argumentenübergabe
In diesem Artikel wird erläutert, wie übergeben [CString](../atl-mfc-shared/reference/cstringt-class.md) von Objekten in Funktionen und wie zurückgegeben `CString` -Objekte aus Funktionen.  
  
##  <a name="_core_cstring_argument.2d.passing_conventions"></a>CString-Argumentübergabe-Konventionen  
 Wenn Sie eine Klassenschnittstelle definieren, müssen Sie für Ihre Memberfunktionen der argumentübergabekonvention ermitteln. Es gibt einige Standardregeln für übergeben und die Rückgabe `CString` Objekte. Wenn Sie die in beschriebenen Regeln folgen [Zeichenfolgen als Funktionseingabe](#_core_strings_as_function_inputs) und [Zeichenfolgen als Funktion Ausgaben](#_core_strings_as_function_outputs), effizienten und korrekten Code müssen.  
  
##  <a name="_core_strings_as_function_inputs"></a>Zeichenfolgen als Funktionseingabe  
 Effiziente und sichere Möglichkeit zum Verwenden einer `CString` Objekt in der aufgerufenen Funktionen ist die Übergabe einer `CString` Objekt an die Funktion. Ungeachtet des Namens einer `CString` Objekt speichert keine Zeichenfolge intern als Zeichenfolge im C-Format, das einen null-Terminator verfügt. Stattdessen ein `CString` Objekt eine sorgfältige verfolgt die Anzahl der Zeichen, die sie hat. Mit `CString` bieten eine `LPCTSTR` Zeiger auf eine Null-terminierte Zeichenfolge ist eine kleine Menge an Arbeit, die Bedeutung, wenn der Code hat zu diesem Zweck ständig werden können. Das Ergebnis ist temporär, da Änderungen an der `CString` Inhalt erklärt die alten Kopien der `LPCTSTR` Zeiger.  
  
 Es sinnvoll in einigen Fällen geben Sie eine Zeichenfolge im C-Format. Beispielsweise kann eine Situation, in denen eine aufgerufene Funktion wird in C# geschrieben und unterstützt keine Objekte, vorhanden sein. In diesem Fall coerce der `CString` Parameter `LPCTSTR`, und die Funktion wird eine C-Stil Null-terminierte Zeichenfolge abzurufen. Können Sie auch die andere Richtung wechseln und erstellen Sie eine `CString` Objekt mithilfe der `CString` , der einen C-Stil Zeichenfolgenparameter akzeptiert.  
  
 Wenn Inhalt der Zeichenfolge durch eine Funktion geändert werden soll, deklarieren Sie den Parameter als Konstanten `CString` Verweis (**CString &**).  
  
##  <a name="_core_strings_as_function_outputs"></a>Zeichenfolgen als Funktion Ausgaben  
 Sie können in der Regel zurückgeben `CString` Objekte von Funktionen, da `CString` Objekte folgen Wertsemantik z. B. primitive Typen. Um eine schreibgeschützte Zeichenfolge zurückzugeben, verwenden Sie eine Konstante `CString` Verweis (**const CString &**). Das folgende Beispiel veranschaulicht die Verwendung von `CString` Parameter und Rückgabetypen:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

