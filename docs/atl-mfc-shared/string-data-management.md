---
title: Eine Zeichenfolge der Datenverwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b42f637c487e27b8658bcd09389eec940bb1df05
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880215"
---
# <a name="string-data-management"></a>Zeichenfolgendatenverwaltung
Visual C++ bietet verschiedene Möglichkeiten zum Verwalten von Zeichenfolgen:  
  
-   [Zeichenfolgenbearbeitung](../c-runtime-library/string-manipulation-crt.md) für die Arbeit mit c-Null-terminierte Zeichenfolgen  
  
-   Win32-API-Funktionen für die Verwaltung von Zeichenfolgen  
  
-   MFC Klasse [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md), die flexible, in der Größe veränderbaren Zeichenfolgenobjekte bereitstellt  
  
-   Klasse [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md), die die gleiche Funktionalität wie eine MFC-unabhängigen String-Objekt bietet `CString`  
  
 Fast alle Programme funktionieren mit Zeichenfolgendaten auf. MFC `CString` Klasse ist häufig die beste Lösung für flexible zeichenfolgenverarbeitung. Ab Version 7.0, `CString` in MFC- oder MFC-unabhängigen-Programmen verwendet werden kann. Der Laufzeit-Bibliothek und `CString` Zeichenfolgensätze Multibytezeichen (Breite) zu können, wie in Unicode oder MBCS-Programmierung zu unterstützen.  
  
 Dieser Artikel beschreibt die allgemeinen Dienste verwendet, die die Klassenbibliothek bietet im Zusammenhang mit zeichenfolgenbearbeitung. In diesem Artikel behandelten Themen umfassen:  
  
-   [Unicode- und MBCS-bereitstellen-Portabilität](#_core_unicode_and_mbcs_provide_portability)  
  
-   [CString-Objekte und const Char-Zeiger](#_core_cstrings_and_const_char_pointers)  
  
-   [CString-Verweiszählung](#_core_cstring_reference_counting)  
  
 Die [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) -Klasse bietet Unterstützung für das Bearbeiten von Zeichenfolgen. Es dient zum Ersetzen und erweitern die Funktionalität, die normalerweise von der C-Laufzeitbibliothek Zeichenfolge-Paket bereitgestellt. Die `CString` -Klasse stellt Member-Funktionen und Operatoren für die Verarbeitung auf dem vereinfachten Zeichenfolge, ähnlich denen in Basic. Die Klasse bietet auch Konstruktoren und Operatoren für erstellen, zuweisen und Vergleichen von `CString`s und C++-standard string-Datentypen. Da `CString` stammt nicht aus `CObject`, können Sie `CString` Objekte unabhängig von den meisten von der Microsoft Foundation Class-Bibliothek (MFC).  
  
 `CString` Führen Sie die Objekte "Wert-Semantik." Ein `CString` Objekt stellt einen eindeutigen Wert. Denken Sie an einer `CString` als eine tatsächliche Zeichenfolge und nicht als ein Zeiger auf eine Zeichenfolge.  
  
 Ein `CString` Objekt stellt eine Sequenz einer Variablen Anzahl von Zeichen dar. `CString` Objekte können als Arrays von Zeichen betrachtet werden.  
  
##  <a name="_core_unicode_and_mbcs_provide_portability"></a> Geben Sie Portabilität, Unicode und MBCS  
 Mit MFC-Version 3.0 und höher, MFC, einschließlich `CString`, für die sowohl Unicode- und multibyte-Zeichensätzen (MBCS) aktiviert ist. Diese Unterstützung erleichtert das Schreiben von portablen Anwendungen, entweder Unicode oder ANSI-Zeichen zu erstellen. Zum Aktivieren dieser Portabilität jedes Zeichen in einer `CString` Objekt weist Typ TCHAR, die folgendermaßen definiert ist `wchar_t` Wenn _UNICODE-Symbol definieren, wenn Sie eine Anwendung erstellen, oder als `char` Wenn nicht. Ein `wchar_t` Zeichen ist 16 Bit breit. MBCS ist aktiviert, wenn Sie mit dem Symbol _MBCS definiert erstellt werden. MFC selbst mit dem _MBCS-Symbol (für die Bibliotheken NAFX) erstellt wird, oder das Symbol "_UNICODE" (für die UAFX-Bibliotheken) definiert.  
  
> [!NOTE]
>  Die `CString` Beispielen in diesem und den zugehörigen Artikeln auf Zeichenfolgen Literalzeichenfolgen, die für Unicode-Portabilität, mit dem _T-Makro, das übersetzt die literale Zeichenfolge in das Formular ordnungsgemäß formatiert:  
  
 `L"literal string"`  
  
> [!NOTE]
>  die der Compiler als Unicode-Zeichenfolge behandelt. Beispielsweise folgender Code:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]  
  
> [!NOTE]
>  als eine Unicode-Zeichenfolge, wenn _UNICODE definiert ist oder als eine ANSI-Zeichenfolge, wenn nicht übersetzt. Weitere Informationen finden Sie im Artikel [Unicode- und Multibyte-Zeichensatz (MBCS) Unterstützung](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
 Ein `CString` Objekt sich INT_MAX (2.147.483.647) Zeichen speichern kann. Der TCHAR-Datentyp dient zum Abrufen oder Festlegen der einzelne Zeichen in einem `CString` Objekt. Im Gegensatz zu Zeichenarrays die `CString` -Klasse verfügt über eine integrierte Memory Allocation-Funktion. Auf diese Weise können `CString` Objekte nach Bedarf automatisch wachsen (d. h. Sie müssen keine wächst Gedanken einer `CString` Objekt längere Zeichenfolgen anpassen).  
  
##  <a name="_core_cstrings_and_const_char_pointers"></a> CString-Objekte und const Char-Zeiger  
 Ein `CString` Objekt kann auch wie eine C-Stil-Literalzeichenfolge fungieren (ein `PCXSTR`, das ist identisch mit **const Char\***  If nicht unter Unicode). Die [CSimpleStringT::operator PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr) Konvertierungsoperator ermöglicht `CString` Objekte, frei für Zeiger auf Zeichen in Funktionsaufrufen ersetzt werden soll. Die **CString (LPCWSTR** `pszSrc` **)** Konstruktor ermöglicht das Zeichenzeigern, ersetzen sollen `CString` Objekte.  
  
 Wird kein Versuch unternommen, um fold `CString` Objekte. Wenn Sie zwei vornehmen `CString` Objekte mit `Chicago`, z. B. die Zeichen in `Chicago` werden an zwei Orten gespeichert. (Dies möglicherweise nicht "true" für zukünftige Versionen von MFC, damit Sie nicht darauf verlassen sollten.)  
  
> [!NOTE]
>  Verwenden der [CSimpleStringT::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) und [CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) Memberfunktionen, wenn Sie müssen den direkten Zugriff auf eine `CString` als einen nicht konstanten Zeiger auf ein Zeichen.  
  
> [!NOTE]
>  Verwenden der [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) und [CStringT::SetSysString](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) Memberfunktionen zu reservieren und BSTR-Objekte, die bei der Automatisierung (früher als OLE-Automatisierung) festzulegen.  
  
> [!NOTE]
>  Ordnen Sie nach Möglichkeit `CString` Objekte, die auf den Frame und nicht auf dem Heap. Dies spart Speicherplatz und die Übergabe von Parametern vereinfacht.  
  
 Die `CString` -Klasse als eine Auflistungsklasse für die Microsoft Foundation Class Library, jedoch nicht implementiert `CString` Objekte können sicherlich als Elemente in Auflistungen gespeichert werden.  
  
##  <a name="_core_cstring_reference_counting"></a> CString-Verweiszählung  
 Ab MFC 4.0 Wenn [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) -Objekte kopiert werden, Kopieren der Daten, statt einen Verweiszähler erhöht. Übergeben von Parametern und die Rückgabe dadurch `CString` Objekte nach Wert effizienter. Diese Vorgänge dazu führen, dass den Kopierkonstruktor, manchmal sogar mehr als einmal aufgerufen werden. Reduziert diesen Aufwand für diese allgemeinen Vorgänge und stellt mithilfe der einen Verweiszähler erhöht `CString` eine attraktivere Option.  
  
 Da jede Kopie zerstört wird, wird der Verweiszähler im ursprünglichen Objekt verringert. Die ursprüngliche `CString` Objekt wird nicht zerstört werden, bis dessen Verweiszähler auf 0 (null) reduziert wird.  
  
 Sie können die `CString` Memberfunktionen [CSimpleStringT::LockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) und [CSimpleStringT::UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) deaktivieren oder aktivieren die verweiszählung.  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

