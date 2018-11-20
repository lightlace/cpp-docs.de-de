---
title: Deklaration/Definition erstellen
ms.date: 10/19/2018
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
ms.openlocfilehash: 59ae3ebc23303554a35eea17c7e28850a4a1499a
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693125"
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
