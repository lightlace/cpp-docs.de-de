---
title: Projekt Build Warnung PRJ0049 | Microsoft Docs
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
ms.openlocfilehash: 8df6fcb8bc5d6517a46279e0bef5036db1e81241
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319809"
---
# <a name="project-build-warning-prj0049"></a>Projektbuildwarnung PRJ0049
Referenzierte Ziel "\<Verweis >' erfordert mindestens .NET Framework \<MinFrameworkVersion > und können nicht im Zielframework des Projekts ausgeführt  
  
 Mithilfe von Visual Studio 2008 erstellte Anwendungen können angeben, welche Version von den [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] sollten sie als Ziel. Wenn Sie einen Verweis auf eine Assembly oder ein Projekt, von denen eine Version von abhängt Hinzufügen der [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] , die neuer ist als die Zielversion, erhalten Sie diese Warnung zur Kompilierzeit.  
  
### <a name="to-correct-this-warning"></a>So beheben Sie diese Warnung  
  
1.  Wählen Sie eine der folgenden Optionen aus:  
  
    -   Ändern Sie das Zielframework des Projekts **Eigenschaftenseiten** Dialogfeld, sodass sie später als oder gleich dem minimalen Frameworkversion alle referenzierten Assemblys und Projekte ist. Weitere Informationen finden Sie unter [Hinzufügen von verweisen](../../ide/adding-references-in-visual-cpp-projects.md).  
  
    -   Entfernen Sie den Verweis auf die Assembly oder das Projekt mit einer minimalen Framework-Version, die älter ist als das Zielframework. Diese Elemente werden mit einem Warnsymbol des Projekts markiert werden **Eigenschaftenseiten**.  
  
## <a name="see-also"></a>Siehe auch  
 [Projektbuildfehler und -warnungen (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)