---
title: Definitionsspeicherort verschieben
ms.date: 11/16/2016
ms.assetid: c6d507ac-c61e-4da2-95c8-d504b42e2520
ms.openlocfilehash: 7957e18732dfae92b7b3ae9cf7ecea441fc3a6b4
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693204"
---
# <a name="move-definition-location"></a>Definitionsspeicherort verschieben

**Zweck:** Sofortiges Verschieben einer Funktionsdefinition zu der entsprechenden Headerdatei.

**Anwendung:** Wenn Sie über eine Funktion verfügen, die in eine Headerdatei verschoben werden soll.

**Grund:** Sie könnten des Feature manuell verschieben, jedoch verschiebt dieses Feature sie automatisch und erstellt bei Bedarf die Headerdatei.

**Vorgehensweise**:

1. Platzieren Sie Ihren Text oder Mauszeiger auf der Funktion, deren Definition Sie verschieben möchten.

   ![Markierter Code](images/movedefinition_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+.**, um das Menü **Schnellaktionen und Refactorings** aufzurufen, und klicken Sie im Kontextmenü auf **Definitionsspeicherort verschieben**.
   * **Maus**
     * Führen Sie einen Rechtsklick aus, und klicken Sie auf das Menü **Schnellaktionen und Refactorings**. Klicken Sie anschließend im Kontextmenü auf **Definitionsspeicherort verschieben**.

1. Die Funktion wird in die entsprechende Headerdatei verschoben. Dies wird Ihnen in einem Vorschaufenster angezeigt.  Wenn die Headerdatei nicht vorhanden ist, wird diese erstellt und im Projekt platziert.

   ![Ergebnis des Erstellens der Deklaration/Definition](images/movedefinition_result.png)
