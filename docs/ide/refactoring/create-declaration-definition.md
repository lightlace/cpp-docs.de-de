---
title: Deklaration/Definition erstellen
ms.date: 10/19/2018
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
ms.openlocfilehash: 56f15ba040314b07450dc8730a913a18361e092f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456965"
---
# <a name="create-declaration--definition"></a>Deklaration/Definition erstellen
**Zweck:** Sofortiges Generieren der Deklaration oder Definition einer Funktion.

**Anwendung:** Wenn Sie über eine Funktion verfügen, die eine Deklaration benötigt und umgekehrt.

**Grund:** Sie können die Deklaration oder Definition manuell erstellen, hiermit wird sie jedoch automatisch erstellt. Außerdem wird bei Bedarf die Header- und die Codedatei erstellt.

**Vorgehensweise**:

1. Platzieren Sie den Text oder Mauszeiger auf der Funktion, für die Sie die Deklaration oder Definition erstellen möchten.

   ![Markierter Code](images/createdefinition_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+.**, um das Menü **Schnellaktionen und Refactorings** aufzurufen, und klicken Sie im Kontextmenü auf **Deklaration/Definition erstellen**.
   * **Maus**
     * Führen Sie einen Rechtsklick aus, und klicken Sie auf das Menü **Schnellaktionen und Refactorings**. Klicken Sie anschließend im Kontextmenü auf **Deklaration/Definition erstellen**.

1. Die Deklaration bzw. Definition der Funktion wird in der Quell- oder Headerdatei erstellt. Dies wird Ihnen in einem Vorschaufenster angezeigt.  Wenn die Quell- oder Headerdatei nicht vorhanden ist, wird diese erstellt und im Projekt platziert.

   ![Ergebnis des Erstellens der Deklaration/Definition](images/createdefinition_result.png)
