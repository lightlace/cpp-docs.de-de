---
title: 'TN017: Zerstören von Fensterobjekten | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.objects
dev_langs:
- C++
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd7b8e9882d682d3e7a9b9162f1f2f84675cd590
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951530"
---
# <a name="tn017-destroying-window-objects"></a>TN017: Zerstören von Fensterobjekten
Dieser Hinweis beschreibt die Verwendung von der [CWnd::PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) Methode. Verwenden Sie diese Methode, wenn Sie benutzerdefinierte Zuordnung von möchten `CWnd`--abgeleitete Objekte. Dieser Hinweis wird auch erläutert, warum der zu verwendende [CWnd:: DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) anstelle von einem C++-Windows-Objekt zu zerstören der **löschen** Operator.  
  
 Wenn Sie die Richtlinien in diesem Thema befolgen, müssen Sie einige Cleanup-Probleme. Diese Probleme können die Folge von Probleme, z. B. C++ Arbeitsspeicher beseitigt Systemressourcen wie Delete/freizugeben beseitigt `HWND`s oder Freigeben von Objekten zu viele Versuche.  
  
## <a name="the-problem"></a>Das Problem  
 Jedes Windows-Objekt (Objekt einer Klasse abgeleitet `CWnd`) stellt ein C++-Objekt und ein `HWND`. C++-Objekte im Heap der Anwendung zugeordnet sind und `HWND`s in Systemressourcen vom Fenstermanager zugeordnet sind. Da es mehrere Möglichkeiten gibt, ein Fensterobjekt zu zerstören, müssen wir angeben, einen Satz von Regeln, die das System verhindern Ressourcen- oder prüfen auf Speicherverluste. Diese Regeln müssen auch Objekte und Windows-Handles verhindern, dass mehr als einmal zerstört wird.  
  
## <a name="destroying-windows"></a>Zerstören von Fenstern  
 Im folgenden sind die zugelassenen zwei Möglichkeiten, ein Windows-Objekt zu zerstören:  
  
-   Aufrufen von `CWnd::DestroyWindow` oder der Windows-API `DestroyWindow`.  
  
-   Löschen explizit mit der **löschen** Operator.  
  
 Der erste Fall tritt weitem der am häufigsten verwendeten. Dieser Fall gilt auch, wenn Ihr Code nicht aufruft `DestroyWindow` direkt. Wenn der Benutzer direkt einem Rahmenfenster schließt, diese Aktion wird die WM_CLOSE-Nachricht generiert und die standardmäßige Antwort auf diese Meldung ist das Aufrufen `DestroyWindow.` , wenn ein übergeordnetes Fenster zerstört wird, ruft Windows `DestroyWindow` für seine untergeordneten Elemente.  
  
 Der zweite Fall, die Verwendung des der **löschen** Operator für Windows-Objekte sollten nur selten der Fall. Im folgenden sind einige Fälle, die Verwendung **löschen** ist die richtige Wahl.  
  
## <a name="auto-cleanup-with-cwndpostncdestroy"></a>Automatische Bereinigung während mit CWnd::PostNcDestroy  
 Wenn das System über ein Windows-Fenster zerstört, ist die letzte Windows-Nachricht an das Fenster WM_NCDESTROY an. Die Standardeinstellung `CWnd` Handler für diese Nachricht wird [zerstören](../mfc/reference/cwnd-class.md#onncdestroy). `OnNcDestroy` Trennen wird die `HWND` aus der C++-Objekt, und rufen Sie die virtuelle Funktion `PostNcDestroy`. Einige Klassen überschreiben dieser Funktion können Sie die C++-Objekt zu löschen.  
  
 Die standardmäßige Implementierung des `CWnd::PostNcDestroy` wird keine Aktion ausgeführt werden, eignet sich für Windows-Objekte, die auf den Stapelrahmen zugeordnet oder in andere Objekte eingebettet sind. Dies ist nicht geeignet für Windows-Objekte, die darauf ausgelegt sind, auf dem Heap ohne beliebiger anderer Objekte zugeordnet werden. Das heißt, ist es nicht geeignet für Windows-Objekte, die in anderen C++-Objekte nicht eingebettet werden.  
  
 Überschreiben Sie diese Klassen, die entwickelt wurden, um allein vom Heap zugewiesen werden die `PostNcDestroy` Methode zum Ausführen einer **löscht**. Diese Anweisung wird die C++-Objekt zugeordneten Arbeitsspeicher freizugeben. Obwohl die Standardeinstellung `CWnd` Destruktoraufrufe `DestroyWindow` Wenn *M_hWnd* ist ungleich NULL, dies führt nicht zu einer Endlosschleife, da das Handle während der Phase Cleanup getrennt und NULL werden kann.  
  
> [!NOTE]
>  Das System in der Regel ruft `CWnd::PostNcDestroy` , nachdem sie die Windows-WM_NCDESTROY-Nachricht verarbeitet und die `HWND` und nicht mehr das C++-Fensterobjekt verbunden sind. Das System wird auch aufrufen, `CWnd::PostNcDestroy` in der Implementierung der meisten [CWnd:: Create](../mfc/reference/cwnd-class.md#create) aufruft, wenn ein Fehler auftritt. Die Regeln für die automatische Bereinigung werden weiter unten in diesem Thema beschrieben.  
  
## <a name="auto-cleanup-classes"></a>Automatisches Cleanup-Klassen  
 Die folgenden Klassen sind nicht für die automatische Bereinigung konzipiert. Sie werden in der Regel in anderen C++-Objekte oder auf dem Stapel eingebettet:  
  
-   Alle Windows-Standardsteuerelemente (`CStatic`, `CEdit`, `CListBox`usw.).  
  
-   Alle untergeordneten Fenster direkt aus dem abgeleiteten `CWnd` (z. B. benutzerdefinierte Steuerelemente).  
  
-   Splitterfenster (`CSplitterWnd`).  
  
-   Standard-Steuerleisten (von abgeleiteten Klassen `CControlBar`, finden Sie unter [technischer Hinweis 31](../mfc/tn031-control-bars.md) für automatisches Löschen von-steuerleistenobjekte aktivieren).  
  
-   Dialogfelder (`CDialog`) für modale Dialogfelder im Stapelrahmen konzipiert.  
  
-   Alle standardmäßigen Dialoge außer `CFindReplaceDialog`.  
  
-   Die Standard-Dialogfelder von ClassWizard erstellt.  
  
 Die folgenden Klassen dienen zur automatischen Bereinigung. Sie werden in der Regel selbst auf dem Heap zugeordnet:  
  
-   Hauptframe Windows (direkt oder indirekt von abgeleiteten `CFrameWnd`).  
  
-   Anzeigen von Windows (direkt oder indirekt von abgeleiteten `CView`).  
  
 Wenn Sie diese Regeln unterbrechen möchten, müssen Sie überschreiben die `PostNcDestroy` Methode in der abgeleiteten Klasse. Um das automatische Cleanup der Klasse hinzugefügt haben, rufen Sie die Basisklasse aus, und führen Sie dann eine **löscht**. Rufen Sie zum Entfernen der automatische Cleanup von Ihrer Klasse `CWnd::PostNcDestroy` direkt anstelle von der `PostNcDestroy` Methode der direkten Basisklasse.  
  
 Die häufigste Verwendung der automatischen Bereinigungsverhalten ändern ist, erstellen ein nicht modales Dialogfeld an, das zugeordnet werden kann, auf dem Heap.  
  
## <a name="when-to-call-delete"></a>Wenn beim Aufruf-löschen  
 Es wird empfohlen, Sie rufen `DestroyWindow` ein Windows-Objekt, die C++-Methode oder globalen zu zerstören `DestroyWindow` API.  
  
 Rufen Sie nicht die globale `DestroyWindow` -API, um ein untergeordnetes MDI-Fenster zu zerstören. Sie sollten die virtuelle Methode verwenden `CWnd::DestroyWindow` stattdessen.  
  
 Verwenden Sie für C++-Fenster-Objekten, das automatische Cleanup nicht durchführen, die **löschen** Operator kann einen Speicherverlust verursachen, wenn Sie versuchen, rufen Sie `DestroyWindow` in die `CWnd::~CWnd` Destruktor, wenn der VTBL nicht ordnungsgemäß abgeleitete Klasse verweist. Dies tritt auf, das System nicht, dass die entsprechenden finden kann aufzurufenden Methode zerstört. Mit `DestroyWindow` anstelle von **löschen** werden diese Probleme vermieden. Da dies eine geringfügige Fehler sein kann, wird im Debugmodus kompiliert die folgende Warnung generieren, wenn Sie gefährdet sind.  
  
```  
Warning: calling DestroyWindow in CWnd::~CWnd  
    OnDestroy or PostNcDestroy in derived class will not be called  
```  
  
 Im Fall von C++-Windows-Objekte, die automatische Bereinigung durchführen, müssen Sie aufrufen `DestroyWindow`. Bei Verwendung der **löschen** Operator direkt, MFC-Diagnose-Speicherbelegungsfunktion benachrichtigt Sie, dass Sie zwei Mal Speicherfreigabe sind. Die zwei Vorkommen sind, Ihre erste expliziter Aufruf und der indirekten Aufruf **löscht** in das automatische Cleanup-Implementierung von `PostNcDestroy`.  
  
 Nach dem Aufruf `DestroyWindow` für ein Objekt nicht automatische Cleanup der C++-Objekt, bleiben, aber *M_hWnd* werden auf NULL. Nach dem Aufruf `DestroyWindow` auf ein Objekt das automatische Cleanup, der C++-Objekt wird nicht mehr vorhanden, freigegeben, indem der C++-Delete-Operator in der Implementierung automatische Cleanup der `PostNcDestroy`.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

