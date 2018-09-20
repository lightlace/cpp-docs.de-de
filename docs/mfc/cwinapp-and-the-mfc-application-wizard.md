---
title: CWinApp und der MFC-Anwendungs-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 009126061856d1165e5d08f6ecc4bd2e7745f2fd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382959"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp und der MFC-Anwendungs-Assistent

Wenn sie eine Skelette-Anwendung erstellt haben, den MFS-Anwendungsassistenten deklariert eine Application-Klasse abgeleitet [CWinApp](../mfc/reference/cwinapp-class.md). Der MFC-Anwendung-Assistent generiert auch eine Implementierungsdatei, die folgenden Elemente enthält:

- Eine meldungszuordnung für die Anwendungsserver-Klasse.

- Eine leere Klasse-Konstruktor.

- Eine Variable, die den und nur ein Objekt der Klasse deklariert.

- Eine Standardimplementierung von Ihrem `InitInstance` Member-Funktion.

Die Anwendungsserver-Klasse befindet sich im Projektheader und main Quelldateien. Die Namen der Klasse und der erstellten Dateien basieren auf den Projektnamen, die Sie im MFC-Anwendungs-Assistenten angeben. Die einfachste Möglichkeit zum Anzeigen des Codes für diese Klassen ist über [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code).

Die standardimplementierungen und eine meldungszuordnung, die bereitgestellt sind für viele Zwecke ausreichend, aber Sie können diese nach Bedarf ändern. Die interessantesten dieser Implementierungen ist das `InitInstance` Member-Funktion. In der Regel wird Code hinzugefügt, auf die Implementierung etwas grob strukturierte `InitInstance`.

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)<br/>
[Überschreibbare CWinApp-Memberfunktionen](../mfc/overridable-cwinapp-member-functions.md)<br/>
[Spezielle CWinApp-Dienste](../mfc/special-cwinapp-services.md)

