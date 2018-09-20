---
title: ExitInstance-Memberfunktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords: []
dev_langs:
- C++
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da411fbecdea0a1e7b8976ca119057204693a9bd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387860"
---
# <a name="exitinstance-member-function"></a>ExitInstance-Memberfunktion

Die [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) Memberfunktion der Klasse [CWinApp](../mfc/reference/cwinapp-class.md) jedes Mal aufgerufen, eine Kopie der Anwendung beendet wird, in der Regel als Ergebnis der Benutzer die Anwendung beendet.

Außer Kraft setzen `ExitInstance` bei Bedarf spezielle Bereinigung-Verarbeitung, wie Graphics Device Interface (GDI) Ressourcen freigegeben oder Freigeben von Speicher während der Ausführung des Programms verwendet. Bereinigen von Standardelementen, z. B. Dokumente und Ansichten, wird jedoch durch das Framework mit andere überschreibbaren-Funktionen für spezielle Bereinigungsaktionen mit diesen Objekten bereitgestellt.

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
