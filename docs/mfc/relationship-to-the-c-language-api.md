---
title: Beziehung zum C-Sprachen-API
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
ms.openlocfilehash: 8f58a33d3accb8eb81299877df1b0c8a4ebe0576
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525696"
---
# <a name="relationship-to-the-c-language-api"></a>Beziehung zum C-Sprachen-API

Die einzigen Merkmals, die die Microsoft Foundation Class (MFC)-Bibliothek neben anderen Klassenbibliotheken für Windows zu festlegt ist, die sehr nahe Zuordnung für die Windows-API, die in der Programmiersprache C geschrieben wird. Darüber hinaus können Sie in der Regel Aufrufe auf die Klassenbibliothek frei mit direkten Aufrufen an die Windows-API kombinieren. Diesen direkte Zugriff bedeutet nicht, jedoch sind die Klassen kein vollständiger Ersatz für diese API. Entwickler müssen immer noch gelegentlich, direkte Aufrufe einiger Windows-Funktionen, z. B. [SetCursor](/windows/desktop/api/winuser/nf-winuser-setcursor) und [GetSystemMetrics](/windows/desktop/api/winuser/nf-winuser-getsystemmetrics), z. B. Eine Windows-Funktion wird durch eine Klassenmemberfunktion eingeschlossen, nur, wenn ein eindeutiger Vorteil zu tun.

Da in einigen Fällen Sie systemeigene Windows-Funktionsaufrufen müssen, sollten Sie in der Programmiersprache C Windows API-Dokumentation zugreifen. Diese Dokumentation ist im Lieferumfang von Microsoft Visual C++.

> [!NOTE]
>  Einen Überblick darüber, wie das Framework für die MFC-Bibliothek arbeitet, finden Sie unter [verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).

## <a name="see-also"></a>Siehe auch

[Allgemeine Prinzipien für den Klassenentwurf](../mfc/general-class-design-philosophy.md)
