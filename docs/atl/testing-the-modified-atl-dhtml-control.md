---
title: Prüfen des geänderten ATL-DHTML-Steuerelements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9730f8ef9bfc89d65ffb89ddbbfe67ce247138e9
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755596"
---
# <a name="testing-the-modified-atl-dhtml-control"></a>Prüfen des geänderten ATL-DHTML-Steuerelements

Testen Sie das neue Steuerelement zu sehen, wie es jetzt funktioniert.

#### <a name="to-build-and-test-the-modified-control"></a>Zum Erstellen und testen das geänderte-Steuerelement

1. Das Projekt neu, und öffnen Sie sie im Test-Container. Finden Sie unter [Testen von Eigenschaften und Ereignisse mit Test Container](../mfc/testing-properties-and-events-with-test-container.md) Informationen zum Zugriff auf Testcontainer.

     Größe des Steuerelements, um alle Schaltflächen anzuzeigen, die Sie hinzugefügt haben.

2. Überprüfen Sie die zwei Schaltflächen, die Sie durch Ändern des HTML-Codes eingefügt. Jede Schaltfläche trägt die Bezeichnung, die Sie in identifiziert [Ändern des ATL-DHTML-Steuerelements](../atl/modifying-the-atl-dhtml-control.md): **aktualisieren** und **HelloHTML**.

3. Testen Sie die zwei neuen Schaltflächen um anzuzeigen, wie sie funktionieren.

Testen Sie jetzt die Methoden, die nicht Teil der Benutzeroberfläche sind.

1. Markieren Sie das Steuerelement aus, damit der Rand aktiviert ist.

2. Auf der **Steuerelement** Menü klicken Sie auf **Methoden aufrufen**.

Die Methoden in der Liste mit der Bezeichnung **Methodenname** sind die Methoden, die der Container aufrufen können: `MethodInvoked` und `GoToURL`. Alle anderen Methoden werden über die Benutzeroberfläche gesteuert.

1. Wählen Sie eine Methode aufzurufen, und klicken Sie auf `Invoke` der Methode Meldungsfeld anzuzeigen oder zu www.microsoft.com zu navigieren.

2. In der **Methoden aufrufen** Dialogfeld klicken Sie auf **schließen**.

Informationen zu den verschiedenen Elementen und Dateien, aus denen ein ATL-DHTML-Steuerelement besteht, finden Sie unter [Identifizieren von Elementen des DHTML-Steuerelementprojekts](../atl/identifying-the-elements-of-the-dhtml-control-project.md).

## <a name="see-also"></a>Siehe auch

[Unterstützung für DHTML-Steuerelement](../atl/atl-support-for-dhtml-controls.md)

