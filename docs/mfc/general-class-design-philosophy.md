---
title: Allgemeine Prinzipien für den Klassenentwurf
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
ms.openlocfilehash: 4dfa11c73703f5f2d3d17f8278610d32178af679
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295075"
---
# <a name="general-class-design-philosophy"></a>Allgemeine Prinzipien für den Klassenentwurf

Microsoft Windows wurde entwickelt, lange bevor die Programmiersprache C++ Popularität einsetzte. Da Tausende von Anwendungen, die Programmiersprache C Windows-Anwendungsprogrammierschnittstelle (API) verwenden, wird diese Schnittstelle für die nächste Zeit beibehalten. Alle C++-Windows-Benutzeroberfläche muss daher auf der prozeduralen Programmiersprache C-API erstellt werden. Dadurch wird sichergestellt, dass die C++-Anwendungen zusammen mit C-Anwendungen verwendet werden können.

Die Microsoft Foundation Class-Bibliothek ist eine objektorientierte Schnittstelle auf Windows, die die folgenden Entwurfsziele erfüllt:

- Deutlich reduziert den Aufwand beim Schreiben einer Anwendung für Windows.

- Die ausführungsgeschwindigkeit ist vergleichbar mit der Programmiersprache C-API.

- Minimale Größe Aufwand.

- Die Möglichkeit, alle Windows-C-Funktion nicht direkt aufrufen.

- Einfacheren Konvertierung vorhandener C#-Anwendungen in C++.

- Die Fähigkeit, von der vorhandenen Basis der Programmiersprache C Windows-Programmierung zu nutzen.

- Einfachere Verwendung von der Windows-API mit C++ als und C.

- Einfacher zu verwendende, aber leistungsstarken Abstraktionen der komplizierte Features wie z. B. ActiveX-Steuerelemente, datenbankunterstützung, drucken, Symbolleisten und Statusleisten.

- "True" Windows-API für C++, die effektiv die C++-Sprachfeatures verwendet.

Weitere Informationen zu den Entwurf der MFC-Bibliothek finden Sie unter:

- [Das Anwendungsframework](../mfc/application-framework.md)

- [Beziehung zum C-Sprachen-API](../mfc/relationship-to-the-c-language-api.md)

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
