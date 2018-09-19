---
title: Allgemeine Klassenentwurf | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fe64ee4d9e6fc678d97c3e9fe37a85e53807541
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416642"
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

