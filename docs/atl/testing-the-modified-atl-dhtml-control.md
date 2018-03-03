---
title: "Testen des geänderten ATL-DHTML-Steuerelements | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c5ecb8526ec82e0f2d18c5306a94dd7f0160803b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="testing-the-modified-atl-dhtml-control"></a>Testen des geänderten ATL-DHTML-Steuerelements
Probieren Sie das neue Steuerelement zu sehen, wie er nun funktioniert.  
  
#### <a name="to-build-and-test-the-modified-control"></a>So erstellen und testen das geänderte Steuerelement  
  
1.  Das Projekt neu, und öffnen Sie es im Testcontainer. Finden Sie unter [Testen von Eigenschaften und Ereignisse mit Test Container](../mfc/testing-properties-and-events-with-test-container.md) Informationen zum Testcontainer zugreifen.  
  
     Ändern Sie die Größe des Steuerelements, um alle Schaltflächen anzeigen, die Sie hinzugefügt haben.  
  
2.  Überprüfen Sie die zwei Schaltflächen, die Sie durch Ändern des HTML-Codes eingefügt. Jede Schaltfläche trägt die Bezeichnung, die Sie in identifizierten [ändern das ATL-DHTML-Steuerelement](../atl/modifying-the-atl-dhtml-control.md): **aktualisieren** und **HelloHTML**.  
  
3.  Die zwei neue Schaltflächen bereit, ihre Funktionsweise zu testen.  
  
 Testen Sie nun die Methoden, die nicht Teil der Benutzeroberfläche sind.  
  
1.  Markieren Sie das Steuerelement aus, damit der Rahmen aktiviert wird.  
  
2.  Auf der **Steuerelement** Menü klicken Sie auf **Methoden aufrufen**.  
  
 Die Methoden in der Liste mit der Bezeichnung **Methodennamen** sind die Methoden, die der Container aufrufen können: `MethodInvoked` und `GoToURL`. Alle anderen Methoden werden über die Benutzeroberfläche gesteuert.  
  
1.  Wählen Sie eine Methode aufrufen, und klicken Sie auf `Invoke` um die Methode Meldungsfeld anzuzeigen oder zu www.microsoft.com zu navigieren.  
  
2.  In der **Methoden aufrufen** (Dialogfeld), klicken Sie auf **schließen**.  
  
 Weitere Informationen finden Sie Informationen zu den verschiedenen Elementen und Dateien, aus denen ein ATL-DHTML-Steuerelement besteht, finden Sie unter [identifizieren die Elemente eines DHTML-Steuerelementprojekts](../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Unterstützung für DHTML-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)

