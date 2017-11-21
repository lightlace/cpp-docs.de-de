---
title: Dialogfeld-Datenaustausch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing dialog boxes
- canceling data exchange
- dialog box data, retrieving
- DDX (dialog data exchange), data exchange mechanism
- dialog boxes [MFC], initializing
- dialog boxes [MFC], retrieving user input using DDX
- dialog box data
- dialog boxes [MFC], data exchange
- CDataExchange class [MFC], using DDX
- DoDataExchange method [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- transferring dialog box data
- DDX (dialog data exchange), canceling
- UpdateData method [MFC]
- retrieving dialog box data [MFC]
ms.assetid: 4675f63b-41d2-45ed-b6c3-235ad8ab924b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e6da394a91eab08f0c79b3edb33132e3c85401af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="dialog-data-exchange"></a>Dialogdatenaustausch
Wenn Sie den DDX-Mechanismus verwenden, Sie legen die Anfangswerte fest des Dialogs objektspezifischen Membervariablen in der Regel in Ihre `OnInitDialog` Ereignishandler oder der Dialogfeldkonstruktor. Sofort das Framework DDX-Mechanismus, bevor das Dialogfeld angezeigt wird, die Werte der Membervariablen an die Steuerelemente im Dialogfeld übertragen, wo sie angezeigt werden, wenn das Dialogfeld angezeigt wird als Antwort auf `DoModal` oder **erstellen** . Die standardmäßige Implementierung des `OnInitDialog` in `CDialog` Aufrufe der `UpdateData` Memberfunktion der Klasse `CWnd` , die Steuerelemente im Dialogfeld zu initialisieren.  
  
 Derselbe Mechanismus überträgt Werte aus den Steuerelementen an die Membervariablen klickt der Benutzer die Schaltfläche "OK" (oder bei jedem Aufruf der `UpdateData` Memberfunktion mit dem Argument **"true"**). Das Dialogfeld Daten Validierungsmechanismus überprüft alle Datenelemente, die für die Sie Validierungsregeln angegeben.  
  
 Die folgende Abbildung veranschaulicht die Dialogfeld-Datenaustausch.  
  
 ![Dialogfeld-Datenaustausch](../mfc/media/vc379d1.gif "vc379d1")  
Dialogdatenaustausch  
  
 `UpdateData`funktioniert in beide Richtungen weisenden Pfeilen, entsprechend den Angaben von der **BOOL** Parameter übergeben. Zum Ausführen der Exchange `UpdateData` richtet eine `CDataExchange` Objekt und Aufrufe eigener Dialogfeldklassen-Überschreibung `CDialog`des `DoDataExchange` Memberfunktion. `DoDataExchange`akzeptiert ein Argument des Typs `CDataExchange`. Die `CDataExchange` an übergebene Objekt `UpdateData` stellt den Kontext des Austausches, definieren solche Informationen wie die Richtung des Austausches dar.  
  
 Wenn Sie (oder einem Code-Assistenten) außer Kraft setzen `DoDataExchange`, geben Sie einen Aufruf einer DDX-Funktion pro Datenmember (Steuerelement). Jede DDX-Funktion weiß, wie für den Datenaustausch in beide Richtungen auf Grundlage des Kontexts vom implementiert die `CDataExchange` Argument zu übergeben, um Ihre `DoDataExchange` von `UpdateData`.  
  
 MFC bietet viele DDX-Funktionen für verschiedene Arten von Exchange. Das folgende Beispiel zeigt eine `DoDataExchange` überschreiben, in welche zwei DDX-Funktionen und eine DDV-Funktion aufgerufen werden:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]  
  
 Die `DDX_` und `DDV_` Zeilen sind eine datenzuordnung. Die gezeigten Beispiel DDX- und DDV Funktionen sind für ein Kontrollkästchen-Steuerelement und ein Eingabefeld Steuerelement.  
  
 Wenn der Benutzer ein modales Dialogfeld, bricht die `OnCancel` Memberfunktion schließt das Dialogfeld und `DoModal` gibt den Wert **IDCANCEL**. In diesem Fall werden keine Daten zwischen des Dialogfelds "" und dem Dialogfeldobjekt ausgetauscht.  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelddaten Dialogdatenaustausch und-Validierung](../mfc/dialog-data-exchange-and-validation.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [Validieren von Dialogfelddaten](../mfc/dialog-data-validation.md)

