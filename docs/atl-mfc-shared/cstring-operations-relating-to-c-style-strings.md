---
title: CString-Vorgänge im Zusammenhang mit Zeichenfolgen im C-Stil | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, basic operations
- MFC [C++], string handling class
- string conversion [C++], C-style strings
- strings [C++], string operations
- standard run-time library string functions
- null values, Null-terminated string conversion
- string functions
- strings [C++], in C
- string arguments
- C-style strings
- strings [C++], class CString
- casting CString objects
ms.assetid: 5048de8a-5298-4891-b8a0-c554b5a3ac1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d0683f82204b11d06b1952913d4dbdb1e4a468d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361813"
---
# <a name="cstring-operations-relating-to-c-style-strings"></a>CString-Vorgänge bei Zeichenfolgen im C-Format
Ein [CString](../atl-mfc-shared/using-cstring.md) -Objekt enthält Zeichenfolgendaten. `CString` erbt den Berechtigungssatz der [Methoden und Operatoren](../atl-mfc-shared/reference/cstringt-class.md) , die in der Klassenvorlage definiert [CStringT](../atl-mfc-shared/reference/cstringt-class.md) zur Bearbeitung von Zeichenfolgendaten. (`CString` ist eine `typedef`, die `CStringT` spezialisiert, damit sie mit den Zeichendaten genutzt werden kann, die `CString` unterstützt.)  
  
 `CString` werden keine Zeichendaten intern als Null-terminierte Zeichenfolge im C-Format gespeichert. Stattdessen zeichnet `CString` die Länge der Zeichendaten auf, sodass die Daten und der benötigte Speicherplatz besser überwacht werden können.  
  
 `CString` akzeptiert die Zeichenfolgen im C-Stil, und bietet Methoden zum Zugreifen auf Zeichendaten als Zeichenfolge im C-Format. Dieses Thema enthält die folgenden Abschnitte, in denen Sie erfahren, wie Sie ein `CString`-Objekt als auf NULL abschließende Zeichenfolge im C-Format verwenden können.  
  
- [Konvertieren von auf Null endende Zeichenfolgen im C-Stil](#_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string)  
  
- [Arbeiten mit Funktionen der standard-Laufzeitbibliothek-Zeichenfolgen](#_core_working_with_standard_run.2d.time_library_string_functions)  
  
- [Direktes Ändern von CString-Inhalten](#_core_modifying_cstring_contents_directly)  
  
- [Verwenden von CString-Objekten mit Variablen argumentsfunktionen](#_core_using_cstring_objects_with_variable_argument_functions)  
  
- [Angeben von formalen CString-Parametern](#_core_specifying_cstring_formal_parameters)  
  
##  <a name="_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string"></a> Verwenden von CString als Null-terminierte Zeichenfolge im C-Format  
 Um ein `CString`-Objekt als Zeichenfolge im C-Format zu verwenden, wandeln Sie das Objekt in `LPCTSTR` um. Im folgenden Beispiel gibt `CString` einen Zeiger auf eine schreibgeschützte auf NULL abschließende Zeichenfolge im C-Format zurück. Die `strcpy`-Funktion fügt eine Kopie der Zeichenfolge im C-Format in der Variablen `myString` ein.  
  
```  
CString aCString = "A string";  
char myString[256];  
strcpy(myString, (LPCTSTR)aCString);
```  
  
 Sie können `CString`-Methoden, z. B. `SetAt`, verwenden, um einzelne Zeichen im Zeichenfolgenobjekt zu ändern. Der `LPCTSTR`-Zeiger ist jedoch nur temporär und wird ungültig, wenn Änderungen an `CString` vorgenommen werden. `CString` kann auch den gültigen Bereich verlassen und automatisch gelöscht werden. Wir empfehlen nach jeder Nutzung einen aktuellen `LPCTSTR`-Zeiger eines `CString`-Objekts abzurufen.  
  
 Gelegentlich benötigen Sie eine Kopie der `CString`-Daten, um direkte Änderungen vorzunehmen. Verwenden Sie die sicherere Funktion `strcpy_s` (oder die Unicode/MBCS-portable Funktion `_tcscpy_s`), um das `CString`-Objekt in einen eigenen Puffer zu kopieren. Dort können die Zeichen sicher geändert werden, wie im folgenden Beispiel gezeigt.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#189](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_1.cpp)]  
  
> [!NOTE]
>  Das dritte Argument `strcpy_s` (oder das Unicode/MBCS-Portable `_tcscpy_s`) handelt es sich um eine `const wchar_t*` (Unicode) oder ein `const char*` (ANSI). Das oben stehende Beispiel übergibt einen `CString` für dieses Argument. Der C++-Compiler wendet automatisch die Konvertierungsfunktion an, die für die `CString`-Klasse definiert wurde, mit der ein `CString` in einen `LPCTSTR` konvertiert wird. Die Fähigkeit, Umwandlungsvorgänge von einem Typ in einen anderen zu definieren, ist eine der nützlichsten Funktionen von C++.  
  
##  <a name="_core_working_with_standard_run.2d.time_library_string_functions"></a> Arbeiten mit Funktionen der Standard-Laufzeitbibliothek-Zeichenfolgen  
 Sie sollten eine `CString`-Methode finden können, um einen beliebigen Zeichenfolgenvorgang durchzuführen, für den Sie die standardmäßigen Funktionen fürC-Laufzeit-Bibliothekszeichenfolgen wie `strcmp` (oder das Unicode/MBCS-portable `_tcscmp`) in Betracht ziehen könnten.  
  
 Wenn Sie die C-Laufzeit-Zeichenfolgenfunktionen verwenden müssen, können Sie im _core_using_cstring_as_a_c.2d.style_null.2d.terminated_string beschriebenen Techniken verwenden. Sie können das `CString`-Objekt in einen entsprechenden Zeichenfolgenpuffer im C-Format kopieren, die Vorgänge durchführen und dann die resultierende Zeichenfolge im C-Format wieder einem `CString`-Objekt zuweisen.  
  
##  <a name="_core_modifying_cstring_contents_directly"></a> Direktes Ändern von CString-Inhalten  
 In den meisten Situationen sollten Sie `CString`-Memberfunktionen verwenden, um die Inhalte eines `CString`-Objekts zu ändern oder um den `CString` in eine Zeichenfolge im C-Format zu konvertieren.  
  
 Es gibt einige Situationen, in denen es sinnvoll ist, die `CString`-Inhalte direkt zu ändern, z. B. wenn Sie mit Betriebssystemfunktionen arbeiten, die einen Zeichenpuffer benötigen.  
  
 Die `GetBuffer`- und `ReleaseBuffer`-Methoden bieten Zugriff auf den internen Zeichenpuffer eines `CString`-Objekts, sodass Sie es direkt ändern können. Die folgenden Schritte zeigen Ihnen, wie Sie diese Funktionen zu diesem Zweck verwenden können.  
  
#### <a name="to-use-getbuffer-and-releasebuffer-to-access-the-internal-character-buffer-of-a-cstring-object"></a>So verwenden Sie GetBuffer und ReleaseBuffer für den Zugriff auf den internen Zeichenpuffer eines CString-Objekts  
  
1.  Rufen Sie `GetBuffer` für ein `CString`-Objekt auf, und geben Sie die Länge des benötigten Puffers an.  
  
2.  Verwenden Sie den von `GetBuffer` zurückgegebenen Zeiger, um Zeichen direkt in das `CString`-Objekt zu schreiben.  
  
3.  Rufen Sie `ReleaseBuffer` für das `CString`-Objekt auf, um alle internen `CString`-Statusinformationen, z. B. die Länge der Zeichenfolge, zu aktualisieren. Nachdem Sie die Inhalte eines `CString`-Objekts direkt geändert haben, müssen Sie `ReleaseBuffer` aufrufen, bevor Sie eine andere `CString`-Memberfunktion aufrufen.  
  
##  <a name="_core_using_cstring_objects_with_variable_argument_functions"></a> Verwenden von CString-Objekten mit Variablen Argumentsfunktionen  
 Einige C-Funktionen haben eine variable Anzahl an Argumenten. Ein bedeutsames Beispiel ist `printf_s`. Aufgrund der Art und Weise, in der diese Funktion deklariert wird, kann der Compiler sich nicht über den Typ der Argumente sicher sein, und er kann nicht bestimmen, welcher Konvertierungsvorgang für jedes Argument durchgeführt werden muss. Daher ist es sehr wichtig, dass Sie eine explizite Typumwandlung verwenden, wenn Sie ein `CString`-Objekt an eine Funktion übergeben, die eine variable Anzahl an Argumenten haben kann.  
  
 Um ein `CString`-Objekt in einer variablen Argumentsfunktion zu verwenden, wandeln Sie `CString` explizit in eine `LPCTSTR`-Zeichenfolge um, wie im folgenden Beispiel gezeigt.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#190](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_2.cpp)]  
  
##  <a name="_core_specifying_cstring_formal_parameters"></a> Angeben von formalen CString-Parametern  
 Bei den meisten Funktionen, die ein Zeichenfolgenargument benötigen, ist es am besten, den formalen Parameter im Funktionsprototypen als einen `const`-Zeiger auf ein Zeichen (`LPCTSTR`) anstelle eines `CString` anzugeben. Wenn ein formaler Parameter als `const`-Zeiger auf ein Zeichen angegeben wird, können Sie entweder einen Zeiger auf ein `TCHAR`-Array, eine Literalzeichenfolge [`"hi there"`], oder ein `CString`-Objekt übergeben. Das `CString`-Objekt wird automatisch in `LPCTSTR` konvertiert. Überall dort, wo Sie einen `LPCTSTR` verwenden können, können Sie auch ein `CString`-Objekt verwenden.  
  
 Sie können auch einen formalen Parameter als einen konstantenzeichenfolgenverweis angeben (d. h. `const CString&`) Wenn das Argument nicht geändert wird. Legen Sie den `const`-Modifizierer ab, wenn die Zeichenfolge mit der Funktion geändert wird. Wenn ein standardmäßiger NULL-Wert gewünscht ist, initialisieren Sie es mit der NULL-Zeichenfolge [`""`], wie nachfolgend beschrieben:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#191](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_3.cpp)]  
  
 Bei den meisten Funktionsergebnissen können Sie einfach ein `CString`-Objekt nach Wert zurückgeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CString-Argumentübergabe](../atl-mfc-shared/cstring-argument-passing.md)

