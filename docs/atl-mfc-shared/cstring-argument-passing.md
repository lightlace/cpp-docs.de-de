---
title: "CString Argument Passing | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "argument passing [C++]"
  - "argument passing [C++], C strings"
  - "arguments [C++], Übergeben"
  - "CString objects, Übergeben von Argumenten"
  - "Funktionen [C++], strings as input/output"
  - "Übergeben von Argumenten, C strings"
  - "string arguments"
  - "Zeichenfolgen [C++], as function input/output"
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CString Argument Passing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel wird beschrieben, wie [CString](../atl-mfc-shared/reference/cstringt-class.md)\-Objekte an Funktionen übergeben werden und wie `CString`\-Objekte von den Funktionen zurückgegeben werden.  
  
##  <a name="_core_cstring_argument.2d.passing_conventions"></a> Argument\-Übergebende Konventionen CString  
 Wenn Sie eine Klassenschnittstelle definieren, müssen Sie die Argument\-übergebende Konvention für die Memberfunktionen bestimmen.  Es gibt mehrere Standardregeln zum Übergeben und Rückgabe von `CString`\-Objekten.  Wenn Sie den Regeln entsprechen, die in [Zeichenfolgen als Funktions\-Eingaben](#_core_strings_as_function_inputs) und in [Zeichenfolgen als Funktions\-Ausgaben](#_core_strings_as_function_outputs) beschrieben werden, haben Sie effizienten, korrekte Code.  
  
##  <a name="_core_strings_as_function_inputs"></a> Zeichenfolgen als Funktions\-Eingaben  
 Die effizienteste und sicherste Methode, ein `CString`\-Objekt in den aufgerufenen Funktionen zu verwenden ist, ein `CString`\-Objekt zur Funktion zu übergeben.  Trotz des Namens speichert ein `CString`\-Objekt eine Zeichenfolge intern nicht als Zeichenfolge in C\-Format, die ein NULL\-Abschlusszeichen aufweist.  Stattdessen verfolgt ein `CString`\-Objekt gesichertes die Anzahl von Zeichen, die sie hat.  `CString` resultieren, erstellen Sie einen `LPCTSTR` Zeiger auf eine auf NULL endende Zeichenfolge ist eine kleine Menge an Arbeit bereit, die bedeutsam werden kann, wenn der Code sie ständig ausführen muss.  Das Ergebnis ist temporär, da jeder Änderung am `CString` Inhalt alte Kopien des Zeigers `LPCTSTR` ungültig werden.  
  
 Es ist sinnvoll, eine Zeichenfolge in C\-Format in einigen Fällen bereitzustellen.  So kann es beispielsweise geben eine Situation, in der eine aufgerufene Funktion in C geschrieben und unterstützt keine Objekte.  In diesem Fall wandeln Sie den `CString`\-Parameter zu `LPCTSTR` um, und die Funktion ruft eine auf NULL endende Zeichenfolge eine ab.  Sie können auch wechseln die andere Richtung und ein `CString`\-Objekt erstellen, indem Sie den `CString`\-Konstruktor verwenden, einer ein Zeichenfolgenparameter akzeptiert.  
  
 Wenn der Zeichenfolgeninhalt durch eine Funktion geändert werden soll, deklarieren Sie den Parameter als Verweis nicht konstanter `CString` \(**CString&**\).  
  
##  <a name="_core_strings_as_function_outputs"></a> Zeichenfolgen als Funktions\-Ausgaben  
 In der Regel können Sie `CString`\-Objekte von den Funktionen zurückgeben, da `CString`\-Objekte Wertsemantik bezeichnet wie primitive Typen folgen.  Wenn eine schreibgeschützte Zeichenfolge zurückzugeben, verwenden Sie einen konstanten Verweis `CString` \(**const CString&**\).  Das folgende Beispiel veranschaulicht die Verwendung von `CString`\-Parameter und Rückgabetyp:  
  
 [!CODE [NVC_ATLMFC_Utilities#197](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#197)]  
  
 [!CODE [NVC_ATLMFC_Utilities#198](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#198)]  
  
## Siehe auch  
 [Zeichenfolgen](../atl-mfc-shared/strings-atl-mfc.md)