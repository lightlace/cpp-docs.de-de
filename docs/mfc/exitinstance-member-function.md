---
title: ExitInstance-Memberfunktion
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: b1c5b3a20f25f909188023ab1650bc41316d7a9f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637735"
---
# <a name="exitinstance-member-function"></a>ExitInstance-Memberfunktion

Die [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) Memberfunktion der Klasse [CWinApp](../mfc/reference/cwinapp-class.md) jedes Mal aufgerufen, eine Kopie der Anwendung beendet wird, in der Regel als Ergebnis der Benutzer die Anwendung beendet.

Außer Kraft setzen `ExitInstance` bei Bedarf spezielle Bereinigung-Verarbeitung, wie Graphics Device Interface (GDI) Ressourcen freigegeben oder Freigeben von Speicher während der Ausführung des Programms verwendet. Bereinigen von Standardelementen, z. B. Dokumente und Ansichten, wird jedoch durch das Framework mit andere überschreibbaren-Funktionen für spezielle Bereinigungsaktionen mit diesen Objekten bereitgestellt.

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
