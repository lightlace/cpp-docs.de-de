---
title: Überschreibbare Memberfunktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed090057394c385dd12825864c5de9ff7d079e29
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345835"
---
# <a name="commonly-overridden-member-functions"></a>Überschreibbare Memberfunktionen
Die folgende Tabelle enthält die wahrscheinlichste Memberfunktionen überschreiben die `CDialog`-Klasse.  
  
### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>Überschreibbare Memberfunktionen der CDialog-Klasse  
  
|Member-Funktion|Meldung an, die reagiert werden soll|Zweck der Außerkraftsetzung|  
|---------------------|----------------------------|-----------------------------|  
|`OnInitDialog`|**WM_INITDIALOG**|Initialisieren Sie das Dialogfeld-Steuerelemente.|  
|`OnOK`|**BN_CLICKED** für Schaltfläche **IDOK**|Reagieren Sie, klickt der Benutzer die Schaltfläche "OK".|  
|`OnCancel`|**BN_CLICKED** für Schaltfläche **IDCANCEL**|Reagiert, wenn der Benutzer auf die Schaltfläche "Abbrechen" klickt.|  
  
 `OnInitDialog`, `OnOK`, und `OnCancel` sind virtuelle Funktionen. Um sie zu überschreiben, deklarieren Sie eine überschreibende Funktion in Ihrer Dialogfeld abgeleitete Klasse mit dem [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).  
  
 `OnInitDialog` wird aufgerufen, kurz bevor das Dialogfeld angezeigt wird. Rufen Sie die Standardeinstellung `OnInitDialog` Handler aus der Außerkraftsetzung – in der Regel als die erste Aktion in den Handler. Standardmäßig `OnInitDialog` gibt **"true"** um anzugeben, dass der Fokus auf das erste Steuerelement im Dialogfeld festgelegt werden soll.  
  
 `OnOK` wird für nicht modale, jedoch nicht modale Dialogfelder in der Regel überschrieben. Wenn Sie diesen Handler für ein modales Dialogfeld überschreiben, rufen Sie die Basisklassenversion aus der Außerkraftsetzung – um sicherzustellen, dass `EndDialog` heißt –, oder rufen Sie `EndDialog` selbst.  
  
 `OnCancel` wird für nicht modale Dialogfelder in der Regel überschrieben.  
  
 Weitere Informationen zu diesen Memberfunktionen finden Sie in der Klasse [CDialog](../mfc/reference/cdialog-class.md) in der *MFC-Referenz* und der Diskussion auf [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Häufig hinzugefügte Memberfunktionen](../mfc/commonly-added-member-functions.md)
