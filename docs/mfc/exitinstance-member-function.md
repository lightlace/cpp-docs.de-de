---
title: ExitInstance-Memberfunktion
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: c76f588b22ad8ffd1d3dae954c5113feffb62a3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405819"
---
# <a name="exitinstance-member-function"></a>ExitInstance-Memberfunktion

Die [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) Memberfunktion der Klasse [CWinApp](../mfc/reference/cwinapp-class.md) jedes Mal aufgerufen, eine Kopie der Anwendung beendet wird, in der Regel als Ergebnis der Benutzer die Anwendung beendet.

Außer Kraft setzen `ExitInstance` bei Bedarf spezielle Bereinigung-Verarbeitung, wie Graphics Device Interface (GDI) Ressourcen freigegeben oder Freigeben von Speicher während der Ausführung des Programms verwendet. Bereinigen von Standardelementen, z. B. Dokumente und Ansichten, wird jedoch durch das Framework mit andere überschreibbaren-Funktionen für spezielle Bereinigungsaktionen mit diesen Objekten bereitgestellt.

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
