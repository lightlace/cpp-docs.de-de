---
title: CString-Argumentenübergabe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86e89a0f4af28606abef8804aeab5d1e2f62e8d8
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882450"
---
# <a name="cstring-argument-passing"></a>CString-Argumentenübergabe
In diesem Artikel wird erläutert, wie übergeben [CString](../atl-mfc-shared/reference/cstringt-class.md) Objekte, Funktionen und das zurückkehren `CString` -Objekte aus Funktionen.  
  
##  <a name="_core_cstring_argument.2d.passing_conventions"></a> CString-Argumentübergabe-Konventionen  
 Wenn Sie eine Klassenschnittstelle definieren, müssen Sie die argumentübergabekonvention für Ihre Memberfunktionen bestimmen. Es gibt einige Standardregeln für die weiter- und Rückgabe von `CString` Objekte. Wenn Sie die in beschriebenen Regeln folgen [Zeichenfolgen als Eingaben der Orchestratorfunktion](#_core_strings_as_function_inputs) und [Zeichenfolgen als Funktionsausgaben](#_core_strings_as_function_outputs), effizienten und korrekten Code müssen.  
  
##  <a name="_core_strings_as_function_inputs"></a> Zeichenfolgen als Eingaben der Orchestratorfunktion  
 Die effiziente und sichere Möglichkeit zum Verwenden einer `CString` -Objekt aufgerufene Funktionen ist das Übergeben einer `CString` Objekt an die Funktion. Trotz des Namens einer `CString` Objekt speichert keine Zeichenfolge intern als Zeichenfolge im C-Stil, die einen null-Terminator verfügt. Stattdessen eine `CString` -Objekt behält eine sorgfältige verfolgen die Anzahl der Zeichen hat. Mit `CString` ein LPCTSTR-Zeiger auf eine Null-terminierte Zeichenfolge ist eine kleine Menge an Arbeit, die erhebliche, wenn Ihr Code dafür ständig werden kann. Das Ergebnis ist temporär, da zum Ändern der `CString` Inhalt erklärt alte Kopien des Zeigers LPCTSTR.  
  
 Es sinnvoll in einigen Fällen geben Sie eine Zeichenfolge im C-Stil. Beispielsweise kann eine Situation, in denen eine aufgerufene Funktion ist in C geschrieben und unterstützt keine Objekte, vorhanden sein. In diesem Fall erzwingen die `CString` Parameter LPCTSTR, und die Funktion eine C-Stil-Null-terminierte Zeichenfolge erhalten. Können Sie auch die andere Richtung wechseln und erstellen Sie eine `CString` -Objekt unter Verwendung der `CString` Konstruktor, der einen C-Stil Zeichenfolgenparameter akzeptiert.  
  
 Wenn der Zeichenfolgeninhalt durch eine Funktion geändert werden, deklarieren Sie den Parameter als Konstanten `CString` Reference (`CString&`).  
  
##  <a name="_core_strings_as_function_outputs"></a> Zeichenfolgen als Funktionsausgabe  
 Sie können in der Regel zurückgeben `CString` Objekte von Funktionen, da `CString` Objekte folgen Wertsemantik z. B. primitive Typen. Um eine schreibgeschützte Zeichenfolge zurückzugeben, verwenden Sie eine Konstante `CString` Reference (`const CString&`). Das folgende Beispiel veranschaulicht die Verwendung von `CString` Parameter und Rückgabetypen:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

