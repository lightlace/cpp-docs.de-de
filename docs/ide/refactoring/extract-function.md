---
title: Extract-Funktion
ms.date: 11/16/2016
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
ms.openlocfilehash: 41a488b067bce750224f3785e311f91d43dc31ca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571027"
---
# <a name="extract-function"></a>Extract-Funktion
**Zweck:** Umwandeln eines Codefragments in dessen eigene Funktion.

**Anwendung:** Wenn Sie über ein Fragment von vorhandenem Code in einer Funktion verfügen, das von einer anderen Funktion aufgerufen werden muss.

**Vorteile**: Sie könnten diesen Code kopieren und einfügen, dies würde jedoch zu einer Duplizierung führen.  Eine bessere Lösung besteht darin, dieses Fragment in eine eigene Funktion umzugestalten, die von anderen Funktion beliebig aufgerufen werden kann.

**Vorgehensweise**:

1. Markieren Sie den zu extrahierenden Code:

   ![Markierter Code](images/extractfunction_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+R** und dann **STRG+M**.  (Beachten Sie, dass Ihre Tastenkombination je nach dem gewählten Profil möglicherweise abweicht.)
     * Drücken Sie **STRG+.**, um das Menü **Schnellaktionen und Refactorings** aufzurufen, und klicken Sie im Kontextmenü auf **Funktion extrahieren (experimentell)**.
   * **Maus**
     * Klicken Sie auf **Bearbeiten > Umgestalten > Funktion extrahieren (experimentell)**.
     * Klicken Sie mit der rechten Maustaste auf den Code, und klicken Sie auf das Menü **Schnellaktionen und Refactorings**. Klicken Sie dann im Kontextmenü auf **Funktion extrahieren (experimentell)**.
     * Klicken Sie auf das ![Glühbirnensymbol](images/bulb.png), das am linken Rand angezeigt wird, und klicken Sie im Kontextmenü auf **Funktion extrahieren (experimentell)**.

1. Geben Sie im Fenster **Funktion/Methode extrahieren (experimentell)** den neuen Funktionsnamen ein, wählen Sie aus, wo der Code platziert werden soll, und klicken Sie auf **OK**.

   ![Dialogfeld „Funktion extrahieren“](images/extractfunction_dialog.png)

1. Die neue Funktion wird am angegebenen Ort erstellt, ein Funktionsprototyp wird in der entsprechenden Headerdatei erstellt und der ursprüngliche Code wird so geändert, dass er die Funktion aufruft.

   ![Ergebnis der Extract-Funktion](images/extractfunction_result.png)
