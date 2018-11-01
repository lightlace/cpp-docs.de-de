---
title: Active Technology und DLLs
ms.date: 11/04/2016
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
ms.openlocfilehash: 270c64df9af792a73acf1ad408aca02e7fadc30f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535810"
---
# <a name="active-technology-and-dlls"></a>Active Technology und DLLs

Active Technology kann Objektserver vollständig innerhalb einer DLL implementiert werden. Dieser Typ des Servers wird in-Process-Server aufgerufen. MFC unterstützt vollständig in-Process-Server für alle Funktionen der visuellen Bearbeitung nicht hauptsächlich deshalb, weil Active-Technologie eine Möglichkeit, ein Server für Sie hook Hauptnachrichtenschleife des Containers nicht bereitstellt. MFC ist erforderlich, den Zugriff auf die Container-Anwendung-Nachrichtenschleife, Zugriffstasten und leerlaufzeitverarbeitung zu behandeln.

Wenn Sie einen Automatisierungsserver schreiben und der Server keine Benutzeroberfläche hat, können Sie Ihren Server in-Process-Server und vollständig abgelegt, um eine DLL-Datei.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Automatisierungsserver](../mfc/automation-servers.md)

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](../build/dlls-in-visual-cpp.md)