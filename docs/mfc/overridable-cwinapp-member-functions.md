---
title: Überschreibbare CWinApp-Memberfunktionen
ms.date: 11/04/2016
f1_keywords:
- CWinApp
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 35db009f86a0cb984f70a349a3ecdd93bfefb0f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297080"
---
# <a name="overridable-cwinapp-member-functions"></a>Überschreibbare CWinApp-Memberfunktionen

[CWinApp](../mfc/reference/cwinapp-class.md) bietet mehrere wichtige überschreibbare Memberfunktionen (`CWinApp` überschreibt diese Member von Klasse [CWinThread](../mfc/reference/cwinthread-class.md), von dem `CWinApp` abgeleitet ist):

- [InitInstance](../mfc/initinstance-member-function.md)

- [Run](../mfc/run-member-function.md)

- [ExitInstance](../mfc/exitinstance-member-function.md)

- [OnIdle](../mfc/onidle-member-function.md)

Die einzige `CWinApp` Memberfunktion, die Sie überschreiben müssen, ist `InitInstance`.

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
