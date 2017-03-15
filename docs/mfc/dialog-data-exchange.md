---
title: "Dialogdatenaustausch | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Abbruch des Datenaustauschs"
  - "Erfassen der Benutzereingabe"
  - "CDataExchange-Klasse, Mit DDX"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch), Abbrechen"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch), Datenaustauschmechanismus"
  - "Dialogfelddaten"
  - "Dialogfelddaten, Abrufen"
  - "Dialogfelder, Datenaustausch"
  - "Dialogfelder, Initialisieren"
  - "Dialogfelder, Abrufen der Benutzereingabe mit DDX"
  - "DoDataExchange-Methode"
  - "Initialisieren von Dialogfeldern"
  - "Abrufen von Dialogfelddaten"
  - "Übertragung von Dialogfelddaten"
  - "UpdateData-Methode"
  - "Benutzereingabe, Abrufen aus MFC-Dialogfeldern"
ms.assetid: 4675f63b-41d2-45ed-b6c3-235ad8ab924b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Dialogdatenaustausch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie den DDX\-Mechanismus verwenden, legen Sie die Anfangswerte der Membervariablen des Dialogfeldobjekts, in der Regel im `OnInitDialog`\-Handler oder im Dialogfeldkonstruktor.  Sofort bevor das Dialogfeld angezeigt wird, überträgt der das Framework des DDX\-Mechanismus die Werte der Membervariablen an Steuerelemente im Dialogfeld, in dem sie angezeigt werden, wenn das Dialogfeld selbst in Reaktion auf `DoModal` oder **Erstellen** angezeigt.  Die Standardimplementierung von `OnInitDialog` in `CDialog` ruft die `UpdateData`\-Memberfunktion der Klasse `CWnd` auf, um die Steuerelemente im Dialogfeld zu initialisieren.  
  
 Derselbe Mechanismus überträgt Werte von Steuerelementen auf Membervariablen, wenn der Benutzer auf die Schaltfläche OK klickt \(oder, wenn Sie die `UpdateData` mit dem Argument **TRUE**\-Memberfunktion aufrufen\).  Der Dialogfelddatenvalidierungsmechanismus überprüft alle Datenelemente, für die Sie Validierungsregeln angegeben haben.  
  
 Die folgende Abbildung veranschaulicht den Dialogdatenaustausch.  
  
 ![Dialogfeld&#45;Datenaustausch](../mfc/media/vc379d1.png "vc379D1")  
Datenaustausch \(Dialogfeld\)  
  
 `UpdateData` funktioniert in beide Richtungen, wie durch den **BOOL**\-Parameter angegeben, der an sie übergeben wird.  So den Austausch, die `UpdateData` Setups ein `CDataExchange`\-Objekt und die Aufrufe durchführen die Überschreibung der Dialogfeldklasse Memberfunktion von `CDialog``DoDataExchange`.  `DoDataExchange` akzeptiert ein Argument des Typs `CDataExchange`.  Das `CDataExchange`\-Objekt, das an `UpdateData` übergeben wird, wird der Kontext des Austausch dar und definiert solche Informationen wie die Richtung des Austausch.  
  
 Wenn Sie ein \(oder Code\-Assistent `DoDataExchange`\) überschreiben, geben Sie einen Aufruf einer DDX\-Funktion pro an Datenmember \(Steuerelement\).  Jede DDX\-Funktion kann für den Datenaustausch in beide Richtungen basierend auf dem Kontext, der vom `CDataExchange`\-Argument angegeben wird, das dem `DoDataExchange` von `UpdateData` übergeben wird.  
  
 MFC stellt viele DDX\-Funktionen für unterschiedliche Arten des Austausch bereit.  Im folgenden Beispiel wird eine `DoDataExchange` \- Überschreibung an, in der zwei DDX\-Funktionen und eine DDV\-Funktion aufgerufen werden:  
  
 [!CODE [NVC_MFCControlLadenDialog#49](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#49)]  
  
 Die `DDX_` und `DDV_` Zeilen sind eine Datenumsetzung.  Das Beispiel DDX und angezeigte DDV\-Funktionen sind für ein Checkbox\-Steuerelement und ein Eingabefeldsteuerelement, bzw.  
  
 Wenn der Benutzer ein modales Dialogfeld abbricht, beendet die `OnCancel`\-Memberfunktion das Dialogfeld und `DoModal` gibt den Wert **IDCANCEL** zurück.  In diesem Fall werden keine Daten zwischen dem Dialogfeld und im Dialogfeldobjekt ausgetauscht.  
  
## Siehe auch  
 [Dialogdatenaustausch und \-validierung](../mfc/dialog-data-exchange-and-validation.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [Validieren von Dialogfelddaten](../mfc/dialog-data-validation.md)