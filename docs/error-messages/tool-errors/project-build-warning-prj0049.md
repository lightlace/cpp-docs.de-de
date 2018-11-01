---
title: Projektbuildwarnung PRJ0049
ms.date: 11/04/2016
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
ms.openlocfilehash: a451b7fe7b2f7cd89f8898232badf0d3b7e9f138
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447215"
---
# <a name="project-build-warning-prj0049"></a>Projektbuildwarnung PRJ0049

Referenzierte Ziel '\<Verweis >' erfordert .NET Framework \<MinFrameworkVersion > und kann nicht auf dem Zielframework des Projekts ausgeführt werden

Mithilfe von Visual Studio 2008 erstellte Anwendungen können angeben, welche Version von .NET Framework sie soll. Wenn Sie einen Verweis auf eine Assembly oder ein Projekt, von denen eine Version von .NET Framework abhängt, die höher als die Zielversion ist fügen, erhalten Sie diese Warnung zum Zeitpunkt der Kompilierung.

### <a name="to-correct-this-warning"></a>Um diese Warnung zu korrigieren.

1. Wählen Sie eine der folgenden Optionen aus:

   - Ändern Sie das Zielframework des Projekts **Eigenschaftenseiten** Dialogfeld, sodass sie später als oder gleich dem minimalen Frameworkversion alle referenzierten Assemblys und Projekte ist. Weitere Informationen finden Sie unter [Hinzufügen von verweisen](../../ide/adding-references-in-visual-cpp-projects.md).

   - Entfernen Sie den Verweis auf die Assembly oder das Projekt mit einer minimalen Framework-Version, die älter ist als die Zielversion von .NET Framework. Diese Elemente werden mit einem Warnsymbol des Projekts markiert werden **Eigenschaftenseiten**.

## <a name="see-also"></a>Siehe auch

[Projektbuildfehler und -warnungen (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)