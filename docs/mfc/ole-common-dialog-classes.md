---
title: OLE-Common-Dialogfeldklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- ActiveX classes [MFC]
- dialog classes [MFC], OLE
- OLE common dialog classes [MFC]
- common dialog classes [MFC]
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: db64f8c3e2c310b306a1be4696a5c4c7d2cea4f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ole-common-dialog-classes"></a>OLE-Common-Dialogfeldklassen
Diese Klassen Behandeln allgemeiner OLE durch Implementieren einer Reihe von OLE-Standarddialogfelder. Sie bieten auch eine einheitliche Benutzeroberfläche für OLE-Funktionen.  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 Vom Framework verwendet, um häufige Anwendungsbereiche für alle OLE-Dialogfelder enthalten. Alle in der Benutzeroberfläche Kategorie Dialogfeldklassen werden von dieser Basisklasse abgeleitet. `COleDialog`kann nicht direkt verwendet werden.  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 Objekt einfügen zeigt das Dialogfeld an, die Standardbenutzeroberfläche für das Einfügen von neuen OLE Verknüpfte oder eingebettete Elemente.  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 Fügen Sie spezielle zeigt das Dialogfeld an, die Standardbenutzeroberfläche zum Implementieren des Befehls Inhalte einfügen bearbeiten.  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Zeigt das Dialogfeld Verknüpfungen bearbeiten, die Standardbenutzeroberfläche zum Ändern von Informationen zu verknüpften Elementen an.  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 Zeigt das Dialogfeld "Symbol ändern", die Standardbenutzeroberfläche ändern, die das OLE zugeordnete Symbol eingebettet oder verknüpften Elements an.  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 Zeigt das Dialogfeld konvertieren, die Standardbenutzeroberfläche für OLE-Elemente von einem Typ in einen anderen konvertieren.  
  
 [COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)  
 Kapselt das Windows allgemeine OLE-Eigenschaften-Dialogfeld an. Häufig verwendete Dialogfelder für OLE-Eigenschaften bieten eine einfache Möglichkeit zum Anzeigen und ändern die Eigenschaften eines Elements ein OLE-Dokument in Übereinstimmung mit den Windows-Standards.  
  
 [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)  
 Zeigt das Update (Dialogfeld), die Standardbenutzeroberfläche für alle Links in einem Dokument aktualisieren. Das Dialogfeld enthält eine Statusanzeige eingeblendet, um festzulegen, wie nahe die Updateprozedur bis zum Abschluss.  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 Ändern der Quelle zeigt das Dialogfeld an, die standard-Benutzeroberfläche für die Quell- oder einer Verknüpfung ändern.  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 Zeigt die Server ausgelastet "und" Server antwortet nicht-Dialogfelder, die Standardbenutzeroberfläche Aufrufe für ausgelastete Anwendungen zu behandeln. Angezeigt in der Regel automatisch von der `COleMessageFilter` Implementierung.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

