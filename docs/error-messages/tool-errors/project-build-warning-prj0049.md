---
title: Project Build Warnung PRJ0049 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 726294f420000ab1d1b98be72d310dfcbfcd04c0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591883"
---
# <a name="project-build-warning-prj0049"></a>Projektbuildwarnung PRJ0049
Referenzierte Ziel '\<Verweis >' erfordert .NET Framework \<MinFrameworkVersion > und kann nicht auf dem Zielframework des Projekts ausgeführt werden  
  
 Mithilfe von Visual Studio 2008 erstellte Anwendungen können angeben, welche Version von .NET Framework sie soll. Wenn Sie einen Verweis auf eine Assembly oder ein Projekt, von denen eine Version von .NET Framework abhängt, die höher als die Zielversion ist fügen, erhalten Sie diese Warnung zum Zeitpunkt der Kompilierung.  
  
### <a name="to-correct-this-warning"></a>Um diese Warnung zu korrigieren.  
  
1.  Wählen Sie eine der folgenden Optionen aus:  
  
    -   Ändern Sie das Zielframework des Projekts **Eigenschaftenseiten** Dialogfeld, sodass sie später als oder gleich dem minimalen Frameworkversion alle referenzierten Assemblys und Projekte ist. Weitere Informationen finden Sie unter [Hinzufügen von verweisen](../../ide/adding-references-in-visual-cpp-projects.md).  
  
    -   Entfernen Sie den Verweis auf die Assembly oder das Projekt mit einer minimalen Framework-Version, die älter ist als die Zielversion von .NET Framework. Diese Elemente werden mit einem Warnsymbol des Projekts markiert werden **Eigenschaftenseiten**.  
  
## <a name="see-also"></a>Siehe auch  
 [Projektbuildfehler und -warnungen (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)