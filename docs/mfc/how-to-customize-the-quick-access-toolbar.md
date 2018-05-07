---
title: 'Vorgehensweise: Anpassen der Symbolleiste für den Schnellzugriff | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- quick access toolbar [MFC], customization
ms.assetid: 2554099b-0c89-4605-9249-31bf9cbcefe0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0faa3a0fb66c4379824a6be190175b10e0415474
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-customize-the-quick-access-toolbar"></a>Gewusst wie: Anpassen der Symbolleiste für den Schnellzugriff
Die schnellen Zugriff Symbolleiste Schnellzugriff ist eine anpassbare Symbolleiste, die eine Reihe von Befehlen enthält, die entweder neben der Schaltfläche "Anwendung" oder auf den Registerkarten Kategorie angezeigt. Die folgende Abbildung zeigt eine typische Symbolleiste für den Schnellzugriff an.  
  
 ![MFC-Menübandsymbolleiste für den Schnellzugriff](../mfc/media/quick_access_toolbar.png "Quick_access_toolbar")  
  
 Um die Symbolleiste für den Schnellzugriff anzupassen, öffnen Sie es in der **Eigenschaften** , ändern Sie deren Befehle ein, und klicken Sie dann das Steuerelement im Menüband in der Vorschau anzeigen.  
  
### <a name="to-open-the-quick-access-toolbar-in-the-properties-window"></a>Um die Symbolleiste für den Schnellzugriff im Eigenschaftenfenster zu öffnen.  
  
1.  In Visual Studio auf die **Ansicht** Menü klicken Sie auf **Ressourcenansicht**.  
  
2.  In **Ressourcenansicht**, doppelklicken Sie auf die menübandressource für die Anzeige auf der Entwurfsoberfläche angezeigt.  
  
3.  Klicken Sie auf der Entwurfsoberfläche, die Symbolleiste für den Schnellzugriff Kontextmenü, und klicken Sie dann auf **Eigenschaften**.  
  
## <a name="quick-access-toolbar-properties"></a>Eigenschaften von Symbolleisten Schnellzugriff  
 In der folgenden Tabelle definiert die Eigenschaften der Symbolleiste für den Schnellzugriff.  
  
|Eigenschaft|Definition|  
|--------------|----------------|  
|Schnellzugriff Position|Gibt die Position der Symbolleiste für den Schnellzugriff an, beim Starten der Anwendung. Die Position kann es sich um **oben** oder **unten** das Steuerelement im Menüband.|  
|Schnellzugriff Elemente|Gibt die Befehle, die für die Symbolleiste für den Schnellzugriff verfügbar sind.|  
  
#### <a name="to-add-or-remove-commands-on-the-quick-access-toolbar"></a>Zum Hinzufügen oder Entfernen von Befehlen auf der Symbolleiste für den Schnellzugriff  
  
1.  In der **Eigenschaften** Fenster, klicken Sie auf **Schnellzugriff Elemente**, und klicken Sie dann auf die Schaltfläche mit den Auslassungspunkten **(...)** .  
  
2.  In der **Schnellzugriff Elemente-Editor** (Dialogfeld), verwenden die **hinzufügen** und **entfernen** Schaltflächen so ändern Sie die Liste der Befehle auf der Symbolleiste für den Schnellzugriff.  
  
3.  Wenn Sie einen Befehl auf der Symbolleiste für den Schnellzugriff und die Symbolleiste für den Schnellzugriff Menü angezeigt werden soll, wählen Sie das Kontrollkästchen neben den Befehl. Wenn Sie den Befehl aus, um nur auf das Menü angezeigt werden soll, deaktivieren Sie das Kontrollkästchen.  
  
## <a name="previewing-the-ribbon"></a>Anzeigen einer Vorschau im Menüband  
 Symbolleiste für den Schnellzugriff werden nicht auf der Entwurfsoberfläche angezeigt. Um diese anzuzeigen, müssen Sie das Menüband in der Vorschau anzeigen oder die Anwendung ausführen.  
  
#### <a name="to-preview-the-ribbon-control"></a>Um das Steuerelement im Menüband in der Vorschau anzeigen  
  
-   Auf der **Ribbon-Editor-Symbolleiste**, klicken Sie auf **Ribbon testen**.  
  
## <a name="see-also"></a>Siehe auch  
 [Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)

