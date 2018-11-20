---
title: Implementieren von rein virtuellen Elementen
ms.date: 11/16/2016
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
ms.openlocfilehash: 59e4519f57a1d9bd9ba1cee1ed6ae41bea785a9f
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51692663"
---
# <a name="implement-pure-virtuals"></a>Implementieren von rein virtuellen Elementen

**Zweck:**: Sofortiges Generieren des Codes, der zum Implementieren aller rein virtuellen Methoden in einer Klasse erforderlich ist.

**Anwendung:** Sie möchten von einer Klasse mit rein virtuellen Funktionen erben.

**Grund**: Sie könnten alle rein virtuellen Features nacheinander manuell implementieren, doch bei diesem Feature werden alle Methodensignaturen automatisch generiert.

**Vorgehensweise**:

1. Platzieren Sie Ihren Text oder Mauszeiger auf der Klasse, in die die rein virtuellen Funktionen der Basisklasse implementiert werden sollen.

   ![Markierter Code](images/virtuals_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+.**, um das Menü **Schnellaktionen und Refactorings** zu öffnen, und klicken Sie im Kontextmenü auf **Alle rein virtuellen Aufrufe für Klasse „*ClassName*“ implementieren**. *ClassName* bezieht sich hier auf den Namen der ausgewählten Klasse.
   * **Maus**
     * Führen Sie einen Rechtsklick aus, und klicken Sie auf das Menü **Schnellaktionen und Refactorings**. Klicken Sie anschließend im Kontextmenü auf **Alle rein virtuellen Aufrufe für Klasse „*ClassName*“ implementieren**. *ClassName* bezieht sich hier auf den Namen der ausgewählten Klasse.

1. Die rein virtuellen Methodensignaturen werden automatisch erstellt und stehen für die Implementierung zur Verfügung.

   ![Ergebnis der Implementierung von rein virtuellen Elementen](images/virtuals_result.png)
