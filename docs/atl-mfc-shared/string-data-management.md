---
title: String-Datenverwaltung | Microsoft Docs
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
ms.openlocfilehash: acf14ebec5417179a94d0a6ffefdb473966f0c2e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361235"
---
# <a name="string-data-management"></a>Zeichenfolgendatenverwaltung
Visual C++ bietet verschiedene Methoden zum Verwalten von Zeichenfolgendaten an:  
  
-   [String Manipulation](../c-runtime-library/string-manipulation-crt.md) für die Arbeit mit Null endende Zeichenfolgen im C-Stil  
  
-   Win32-API-Funktionen zum Verwalten von Zeichenfolgen  
  
-   MFC Klasse [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md), flexible und in der Größe veränderbaren Zeichenfolgenobjekten stellt  
  
-   Klasse [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md), bietet eine MFC-unabhängigen String-Objekt mit die gleiche Funktionalität wie `CString`  
  
 Fast alle Programme mehr mit Zeichenfolgendaten. MFC `CString` Klasse ist häufig die beste Lösung für die flexible Zeichenfolgenbehandlung. Ab Version 7.0, `CString` in MFC oder unabhängig von MFC-Programmen verwendet werden können. Der Laufzeit-Bibliothek und `CString` Zeichenfolgen mit multibyte () Breitzeichen, wie in Unicode oder MBCS-Programmierung zu unterstützen.  
  
 Dieser Artikel beschreibt die allgemeinen Dienste verwendet, die die Klassenbibliothek bietet bis zur zeichenfolgenbearbeitung beziehen. In diesem Artikel behandelten Themen werden behandelt:  
  
-   [Unicode und MBCS bieten Portabilität](#_core_unicode_and_mbcs_provide_portability)  
  
-   [CString-Objekte und const Char-Zeiger](#_core_cstrings_and_const_char_pointers)  
  
-   [CString-Verweiszählung](#_core_cstring_reference_counting)  
  
 Die [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) -Klasse bietet Unterstützung für das Bearbeiten von Zeichenfolgen. Es dient zum Ersetzen und erweitern die Funktionalität, die normalerweise von der C-Laufzeitbibliothek Zeichenfolge-Paket bereitgestellt. Die `CString` Klasse bereitstellt, Member-Funktionen und Operatoren für ähnliche Benutzeroberflächenfeatures Basic vereinfachte Zeichenfolge behandeln. Die Klasse bietet auch Konstruktoren und Operatoren erstellen, zuweisen und Vergleichen von **CString** und standard C++ Zeichenfolgen-Datentypen. Da `CString` stammt nicht aus `CObject`, können Sie `CString` Objekte unabhängig von den meisten der Microsoft Foundation Class-Bibliothek (MFC).  
  
 `CString` Führen Sie die Objekte "Wertsemantik". Ein `CString` -Objekt stellt einen eindeutigen Wert dar. Denken Sie an einer `CString` als eine tatsächliche Zeichenfolge und nicht als ein Zeiger auf eine Zeichenfolge.  
  
 Ein `CString` -Objekt stellt eine Sequenz von eine Variable Anzahl von Zeichen dar. `CString` Objekte können als Arrays von Zeichen betrachtet werden.  
  
##  <a name="_core_unicode_and_mbcs_provide_portability"></a> Unicode und MBCS bieten Portabilität  
 Mit MFC-Version 3.0 und höher, MFC, einschließlich `CString`, für Unicode- und multibyte-Zeichensätzen (MBCS) aktiviert ist. Diese Unterstützung erleichtert es Ihnen das Schreiben von portablen Anwendungen, entweder Unicode oder ANSI-Zeichen zu erstellen. So aktivieren Sie diese Portabilität jedes Zeichen in einem `CString` Objekt ist vom Typ **TCHAR**, die als definiert ist `wchar_t` , wenn Sie das Symbol definieren **_UNICODE** beim Erstellen der Anwendung oder als `char` Wenn dies nicht. Ein `wchar_t` Zeichen ist 16 Bit breit. MBCS ist aktiviert, wenn Sie mit dem Symbol erstellen **_MBCS** definiert. MFC selbst basiert entweder mit der **_MBCS** Symbol (für die NAFX-Bibliotheken) oder die **_UNICODE** Symbol (für die UAFX-Bibliotheken) definiert.  
  
> [!NOTE]
>  Die `CString` Beispielen in diesem und den zugehörigen Artikel auf Zeichenfolgen anzeigen Literalzeichenfolgen ordnungsgemäß für Unicode-Portabilität formatiert, mithilfe der **_T** -Makro, das das Zeichenfolgenliteral in das Formular übersetzt:  
  
 `L"literal string"`  
  
> [!NOTE]
>  die der Compiler als Unicode-Zeichenfolge behandelt. Beispielsweise folgender Code:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]  
  
> [!NOTE]
>  wird als Unicode-Zeichenfolge übersetzt, wenn **_UNICODE** definiert ist, oder als eine ANSI-Zeichenfolge, wenn nicht. Weitere Informationen finden Sie im Artikel [Unicode- und Multibyte-Zeichensätzen (MBCS)-Unterstützung](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
 Ein `CString` Objekt kann bis zu speichern, **INT_MAX** (2.147.483.647) Zeichen. Die **TCHAR** -Datentyp dient zum Abrufen oder Festlegen der einzelne Zeichen innerhalb einer `CString` Objekt. Im Gegensatz zu Zeichenarrays die `CString` -Klasse verfügt über eine integrierte Speicher Allocation-Funktion. Auf diese Weise können `CString` Objekte bei Bedarf automatisch erweitert (d. h., Sie müssen nicht kümmern, wächst eine `CString` Objekt um längere Zeichenfolgen passen).  
  
##  <a name="_core_cstrings_and_const_char_pointers"></a> CString-Objekte und const Char-Zeiger  
 Ein `CString` Objekt kann auch wie eine C-Stil Literalzeichenfolge fungieren (ein `PCXSTR`, also identisch **const Char\***  If nicht unter Unicode). Die [CSimpleStringT::operator PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr) Konvertierungsoperator ermöglicht `CString` Objekte frei für Zeiger auf Zeichen in Funktionsaufrufen ersetzt werden. Die **CString (LPCWSTR** `pszSrc` **)** Konstruktor können Zeichenzeigern, ersetzen sollen `CString` Objekte.  
  
 Wird nicht versucht, fold `CString` Objekte. Wenn Sie zwei vornehmen `CString` Objekte mit `Chicago`, z. B. die Zeichen in `Chicago` an zwei Orten gespeichert sind. (Dies möglicherweise nicht "true" für zukünftige Versionen von MFC, daher sollten Sie nicht davon abhängen.)  
  
> [!NOTE]
>  Verwenden der [CSimpleStringT::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) und [CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) Member-Funktion bei müssen Sie den direkten Zugriff auf eine `CString` als einen nicht konstanten Zeiger auf ein Zeichen.  
  
> [!NOTE]
>  Verwenden der [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) und [CStringT::SetSysString](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) Memberfunktionen zuordnen und festlegen `BSTR` in Automation (früher OLE-Automatisierung) verwendeten Objekte.  
  
> [!NOTE]
>  Reservieren Sie nach Möglichkeit `CString` Objekte auf den Frame und nicht auf dem Heap. Dies spart Arbeitsspeicher und übergeben von Parametern vereinfacht.  
  
 Die `CString` Klasse wird nicht jedoch als eine Auflistungsklasse Microsoft Foundation Class-Bibliothek implementiert `CString` Objekte als Elemente in Auflistungen sicher gespeichert werden können.  
  
##  <a name="_core_cstring_reference_counting"></a> CString-Verweiszählung  
 Ab MFC 4.0 Wenn [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) Objekte kopiert werden, Kopieren der Daten, statt einen Verweiszähler erhöht. Dadurch wird die Übergabe von Parametern und die Rückgabe von `CString` Objekte nach Wert effizienter. Diese Vorgänge dazu führen, dass den Kopierkonstruktor, mitunter sogar mehr als einmal aufgerufen werden. Einen Verweiszähler erhöht Verwaltungsaufwand für diese allgemeine Vorgänge reduziert und lässt sich mit `CString` eine attraktiver-Option.  
  
 Da jede Kopie zerstört wird, wird der Verweiszähler im ursprünglichen Objekt verringert. Die ursprüngliche `CString` Objekt wird nicht zerstört, bis der entsprechende Verweiszähler auf 0 (null) reduziert wird.  
  
 Sie können die `CString` Memberfunktionen [CSimpleStringT::LockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) und [CSimpleStringT::UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) verweiszählung aktivieren oder deaktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

