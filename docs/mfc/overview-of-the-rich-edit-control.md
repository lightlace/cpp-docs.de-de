---
title: Übersicht über das RichEdit-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 143fc93fb07d9ac7c4e803bbce426c114c02bfeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="overview-of-the-rich-edit-control"></a>Übersicht über das RichEdit-Steuerelement
> [!IMPORTANT]
>  Bei Verwendung von einem rich-Edit-Steuerelement in einem Dialogfeld (unabhängig davon, ob Ihre Anwendung SDI, MDI oder Dialogfeldern basierende), rufen Sie [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) nach bevor das Dialogfeld im Feld angezeigt wird. Eine typische zum Aufrufen dieser Funktion ist in Ihrem Programms `InitInstance` Memberfunktion. Sie müssen nicht jedes Mal aufrufen, Sie das Dialogfeld nur beim ersten Mal anzeigen. Sie müssen keine Aufrufen `AfxInitRichEdit` bei Verwendung mit `CRichEditView`.  
  
 Rich-edit-Steuerelemente ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) Geben Sie eine Programmierschnittstelle für Formatieren von Text. Komponenten der Benutzeroberfläche zum Formatierungsvorgänge für den Benutzer verfügbar machen muss jedoch eine Anwendung implementiert werden. D. h., das Rich-edit Steuerelement unterstützt die Zeichen- oder Absatz Attribute des markierten Texts zu ändern. Einige Beispiele für Zeichen, die Attribute sind fett, kursiv, Schriftfamilie und Schriftgrad. Beispiele für Absatzattribute: Ausrichtung, Ränder und Tabstopps. Es ist jedoch entscheiden, ob Sie die Benutzeroberfläche bereitstellen, ob dieses Symbolleisten-Schaltflächen, Menüelemente oder ein Dialogfeld Format Zeichen ist. Es gibt auch Funktionen, um das rich-Edit-Steuerelement für die Attribute der aktuellen Auswahl abzufragen. Verwenden Sie diese Funktionen zum Anzeigen der aktuellen Einstellungen für die Attribute, z. B. ein Häkchen auf dem UI-Befehl festlegen, wenn die Auswahl der fett formatierte zeichenformatierung-Attribut verfügt.  
  
 Weitere Informationen zu Zeichen- und absatzformatierung, finden Sie unter [Zeichenformat](../mfc/character-formatting-in-rich-edit-controls.md) und [Absatzformatierung](../mfc/paragraph-formatting-in-rich-edit-controls.md) weiter unten in diesem Thema.  
  
 Rich-edit-Steuerelemente unterstützen fast alle Vorgänge und benachrichtigungsmeldungen mit mehrzeilige Bearbeitungssteuerelemente verwendet. Folglich-Anwendungen, die bereits mit Bearbeitungssteuerelementen problemlos geändert werden können zur Verwendung von Rich edit-Steuerelemente. Zusätzliche Nachrichten und Benachrichtigungen können Anwendungen die Funktionalität nur für rich Edit-Steuerelemente zugreifen. Informationen zu Bearbeitungssteuerelementen, finden Sie unter [CEdit](../mfc/reference/cedit-class.md).  
  
 Weitere Informationen zu Benachrichtigungen, finden Sie unter [Benachrichtigungen von einem RichEdit-Steuerelement](../mfc/notifications-from-a-rich-edit-control.md) weiter unten in diesem Thema.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

