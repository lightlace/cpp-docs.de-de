---
title: "Steuerelementtypen für die Struktur | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TVS_SINGLEEXPAND
- TVS_LINESATROOT
- TVS_HASBUTTONS
- TVS_NOTOOLTIPS
- TVS_HASLINES
dev_langs: C++
helpviewer_keywords:
- TVS_LINESATROOT [MFC]
- styles [MFC], CTreeCtrl
- styles [MFC], tree control
- TVS_HASLINES
- TVS_SINGLEEXPAND
- CTreeCtrl class [MFC], styles
- TVS_EDITLABELS [MFC]
- TVS_NOTOOLTIPS [MFC]
- TVS_HASBUTTONS [MFC]
- tree controls [MFC], styles
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eabc479d68134e3e0cc94a4236cb9ab3270cd2e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="tree-control-styles"></a>Struktursteuerelementstile
Strukturansicht ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) Stile steuern Aspekte der Darstellung eine Struktur des Steuerelements. Bei der Erstellung des Strukturansicht-Steuerelements, legen Sie die anfänglichen Formate. Abrufen und ändern Sie die Stile nach dem Erstellen des Strukturansicht-Steuerelements mithilfe der [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) und [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows-Funktionen, die Angabe **GWL_STYLE** für die `nIndex` Parameter. Eine vollständige Liste der Formate finden Sie unter [Ansicht Fenster Struktursteuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb760013) im Windows SDK.  
  
 Die **Formate TVS_HASLINES** Stil verbessert die grafische Darstellung der Hierarchie eine Strukturansicht-Steuerelements durch Zeichnen von Linien, die untergeordnete Elemente mit ihren entsprechenden übergeordneten Element verknüpft. Dieses Format jedoch nicht Elemente auf der Stammebene der Hierarchie verknüpft. Zu diesem Zweck müssen Sie zum Kombinieren der **Formate TVS_HASLINES** und **TVS_LINESATROOT** Stile.  
  
 Der Benutzer kann erweitern oder Reduzieren von einem übergeordneten Element der Liste der untergeordneten Elemente durch Doppelklicken auf das übergeordnete Element. Eine Strukturansicht-Steuerelement mit dem **TVS_SINGLEEXPAND** Format bewirkt, dass die zum Erweitern ausgewählt wird und das Element wird deaktiviert, um zu reduzieren. Wenn die Maus verwendet wird, um das ausgewählte Element per Einzelklick und dieses Element wird geschlossen, wird er erweitert werden. Wenn das ausgewählte Element Single-geklickt wird, wenn er geöffnet ist, wird er reduziert werden.  
  
 Eine Strukturansicht-Steuerelement mit dem **TVS_HASBUTTONS** Stil Fügt eine Schaltfläche auf der linken Seite des jedem übergeordneten Element. Der Benutzer kann die Schaltfläche zum Erweitern oder reduzieren die untergeordneten Elemente als Alternative zum Doppelklicken Sie auf dem übergeordneten Element klicken. **TVS_HASBUTTONS** Elemente auf der Stammebene der Hierarchie nicht Schaltflächen hinzu. Zu diesem Zweck müssen Sie kombinieren **Formate TVS_HASLINES**, **TVS_LINESATROOT**, und **TVS_HASBUTTONS**.  
  
 Die **TVS_EDITLABELS** Stil ermöglicht es dem Benutzer, die Bezeichnungen des Strukturansicht-Steuerelements zu bearbeiten. Weitere Informationen zum Bearbeiten von Bezeichnungen finden Sie unter [Struktur Bearbeitungssteuerelement Bezeichnung](../mfc/tree-control-label-editing.md) weiter unten in diesem Thema.  
  
 Die **TVS_NOTOOLTIPS** Stil deaktiviert die automatische QuickInfo-Funktion des Strukturansicht-Steuerelemente. Diese Funktion zeigt automatisch eine QuickInfo, die den Titel des Elements unter dem Cursor enthält, wenn der gesamte Titel zurzeit nicht sichtbar ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

