---
title: "TN017: Zerst&#246;ren von Fensterobjekten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.objects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zerstören von Fenstern"
  - "PostNcDestroy-Methode"
  - "TN017"
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# TN017: Zerst&#246;ren von Fensterobjekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis beschreibt die Verwendung der [CWnd::PostNcDestroy](../Topic/CWnd::PostNcDestroy.md)\-Methode.  Verwenden Sie diese Methode, wenn Sie benutzerdefinierte Zuordnung von `CWnd` abgeleitete Objekte ausführen möchten.  Dieser Hinweis wird auch beschrieben, warum Sie [CWnd::DestroyWindow](../Topic/CWnd::DestroyWindow.md) verwenden sollten, um ein C\+\+\-Objekt Windows anstelle des Operators `delete` zu zerstören.  
  
 Wenn Sie die Richtlinien in diesem Thema ausführen, erhalten Sie einige Bereinigungsprobleme.  Diese Probleme können sich von Problemen z Vergessen löschen\/freier C\+\+\-Arbeitsspeicher, beseitigt, Systemressourcen wie `HWND`s oder freizugeben, Objekte zu oft freigeben führen.  
  
## Das Problem  
 Jedes Window\-Objekt \(Objekt einer Klasse abgeleitet von `CWnd`\) stellt sowohl ein C\+\+\-Objekt und `HWND` dar.  C\+\+\-Objekte werden im Heap der Anwendung verknüpft und werden `HWND`s in den Systemressourcen der Fenster\-Manager zugeordnet.  Da es mehrere Möglichkeiten gibt, ein Window\-Objekt zu zerstören, müssen Sie einen Satz von Regeln schaffen, die Speicherverluste Systemressource oder verhindern.  Diese Regeln müssen auch verhindern, dass Objekte Windows\-Handles und mehrfach zerstört.  
  
## Zerstören von Windows  
 Dies sind die zwei zulässigen Möglichkeiten, ein Windows\-Objekt zu zerstören:  
  
-   Aufrufen von `CWnd::DestroyWindow` oder von Windows\-API `DestroyWindow`.  
  
-   Explizit, Löschen mit dem Operator `delete`.  
  
 Der erste ist Fall bei weitem verbreitetste.  Dieser Fall gilt, wenn der Code nicht `DestroyWindow` direkt aufruft.  Wenn der Benutzer direkt ein Rahmenfenster enthält, generiert diese Aktion die `WM_CLOSE`, und die Meldung Standardantwort zu dieser Nachricht ist, `DestroyWindow.` , wenn ein übergeordnetes Fenster, zerstört, Windows aufzurufen aufruft `DestroyWindow` für alle untergeordneten Elemente.  
  
 Im zweiten Fall, die Verwendung des Operators für Windows `delete`\-Objekten, sollte selten sein.  Im Folgenden werden einige Fälle, in denen `delete` verwenden, ist die richtige Wahl.  
  
## Automatische Bereinigung mit CWnd::PostNcDestroy  
 Wenn vom System ein Windows\-Fenster zerstört, ist der letzte Windows\-Meldung, die an das Fenster gesendet, `WM_NCDESTROY`.  Der standardmäßige `CWnd`\-Handler für diese Nachricht ist [CWnd::OnNcDestroy](../Topic/CWnd::OnNcDestroy.md).  `OnNcDestroy` wird `HWND` vom C\+\+\-Objekt und ruft die virtuelle Funktion `PostNcDestroy` auf.  Einige Klassen überschreiben diese Funktion, um das C\+\+\-Objekt zu löschen.  
  
 Die Standardimplementierung von `CWnd::PostNcDestroy` ist wirkungslos, das für Fensterobjekte sinnvoll ist, die auf dem Stapelrahmen zugeordnet sind oder in andere Objekte eingebettet.  Dies ist nicht für Fensterobjekte geeignet, die entwickelt wurden, auf dem Heap ohne andere Objekte zugeordnet werden.  Das heißt, ist er nicht für Fensterobjekte geeignet, die in anderen Schemas C\+\+\-Objekten eingebettet werden.  
  
 Diese Klassen, die entwickelt wurden, auf der Heapüberschreibung allein zugeordnet werden die `PostNcDestroy`\-Methode, um `delete this` auszuführen.  Diese Anweisung gibt jedes Arbeitsspeicher frei, der dem C\+\+\-Objekt zugeordnet ist.  Obwohl `CWnd` die Standardeinstellung Destruktor `DestroyWindow` aufruft, wenn `m_hWnd` nicht NULL ist, führt dies nicht zu unbegrenzte Rekursion, da das Handle getrennt und während der Bereinigungsphase NULL ist.  
  
> [!NOTE]
>  Das System ruft `CWnd::PostNcDestroy` normalerweise auf, nachdem die Nachricht Windows `WM_NCDESTROY` verarbeitet und `HWND` und das C\+\+\-Fensterobjekt nicht mehr besteht.  Das System ruft auch `CWnd::PostNcDestroy` in der Implementierung der meisten [CWnd::Create](../Topic/CWnd::Create.md) Aufrufe auf, wenn Fehler auftritt.  Die automatische Bereinigungsregeln werden weiter unten in diesem Thema beschrieben.  
  
## Automatische Bereinigungs\-Klassen  
 Die folgenden Klassen sind nicht für AUTOBereinigung vorgesehen.  Sie werden üblicherweise bei anderen C\+\+\-Objekten oder auf dem Stapel eingebettet:  
  
-   Alle Standardwindows\-steuerelemente \(`CStatic`, `CEdit`, `CListBox`, z.\).  
  
-   Alle untergeordneten Fenster wird direkt von `CWnd`, \(z benutzerdefinierte Steuerelemente\).  
  
-   Splitterfenster \(`CSplitterWnd`\).  
  
-   Standardsteuerelementleisten \(Klassen, die von `CControlBar` abgeleitet werden, finden Sie unter [Technischer Hinweis 31](../mfc/tn031-control-bars.md) für das Aktivieren von AUTODELETE für Steuerleistenobjekte\).  
  
-   Dialogfelder \(`CDialog`\) entworfen für modale Dialogfelder im Stapelrahmen.  
  
-   Alle Standarddialogfelder schließen `CFindReplaceDialog` aus.  
  
-   Die durch die Standarddialogfelder erstellt.  
  
 Die folgenden Klassen sind zur AUTOBereinigung vorgesehen.  Sie werden in der Regel selbst auf dem Heap reserviert:  
  
-   Hauptrahmenfenster \(direkt oder indirekt von `CFrameWnd` abgeleitet sind\).  
  
-   Ansichtsfenster \(direkt oder indirekt von `CView` abgeleitet sind\).  
  
 Wenn Sie diese Regeln unterbrechen möchten, müssen Sie die `PostNcDestroy`\-Methode in der abgeleiteten Klasse überschreiben.  Um AUTOBereinigung der Klasse hinzuzufügen, rufen Sie die Basisklasse auf und führen Sie dann `delete this`.  Um AUTOBereinigung von Ihrer Klasse zu entfernen, rufen Sie `CWnd::PostNcDestroy` unmittelbar statt der direkten `PostNcDestroy`\-Methode der Basisklasse auf.  
  
 Die häufigste Verwendung von Ändern des automatischen Bereinigungsverhaltens ist, ein nicht modales Dialogfeld zu erstellen, für das Heapspeicher reserviert werden kann.  
  
## Wann Löschen aufruft  
 Es wird empfohlen, dass Sie `DestroyWindow` aufrufen, um ein Windows\-Objekt zu zerstören, entweder die C\+\+\-Methode oder die globale `DestroyWindow` API.  
  
 Rufen Sie die globale `DestroyWindow` API auf, um ein untergeordnetes MDI\-Fenster zu zerstören.  Sie können die virtuelle Methode `CWnd::DestroyWindow` verwenden.  
  
 Für C\+\+\-Fensterobjekte, die nicht AUTOBereinigung ausführen, mithilfe des Operators `delete` kann Speicherverluste verursachen, wenn Sie versuchen, `DestroyWindow` in `CWnd::~CWnd` Destruktor aufrufen kann, wenn das VTBL nicht auf der richtig abgeleiteten Klasse veranschaulicht.  Dies tritt auf, da das System das entsprechende nicht finden kann zerstören Methode, um sie aufzurufen.  Mit `DestroyWindow` anstelle `delete` kann diese Probleme.  Da dieser ein detaillierter Fehler sein kann, generiert die Kompilierung im Debugmodus die folgende Warnung, wenn Sie gefährdet sind.  
  
```  
Warning: calling DestroyWindow in CWnd::~CWnd  
   OnDestroy or PostNcDestroy in derived class will not be called  
```  
  
 Bei Objekten C\+\+ Windows, die AUTOBereinigung ausführen, müssen Sie `DestroyWindow` aufrufen.  Wenn Sie den Operator `delete` direkt verwenden, benachrichtigt die MFC\-Diagnosespeicherbelegungsfunktion Sie, dass Sie zweimal Speicher freigeben.  Die zwei Vorkommen sind Sie zunächst expliziter Aufruf der indirekten Aufruf von `delete this` in der AUTOBereinigungsimplementierung von `PostNcDestroy`.  
  
 Nachdem es `DestroyWindow` auf einem Nicht\-AUTOBereinigungsobjekt aufgerufen hat, ist das C\+\+\-Objekt noch dreht, aber `m_hWnd` ist NULL.  Nachdem die `DestroyWindow` auf einem AUTOBereinigungsobjekt aufgerufen hat, wird das C\+\+\-Objekt gegangen, freigegeben durch den C\+\+\-delet\-Operator in der AUTOBereinigungsimplementierung von `PostNcDestroy`.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)