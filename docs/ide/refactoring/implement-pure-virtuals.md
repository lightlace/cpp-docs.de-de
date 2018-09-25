---
title: Implementieren von rein virtuellen Elementen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 234ae9a67bcbc60ea156fbacb5169d0bd1573a91
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442759"
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
