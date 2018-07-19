---
title: Empfehlungen für die Wahl zwischen ATL- und MFC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 116f2066b98951aa2a470021f5527542ac8cbe46
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357322"
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>Empfehlungen für die Wahl zwischen ATL- und MFC
Wenn Sie Komponenten und Anwendungen zu entwickeln, können Sie zwischen zwei Ansätze auswählen – ATL- und MFC (Microsoft Foundation Class-Bibliothek).  
  
## <a name="using-atl"></a>Verwendung von ATL  
 ATL handelt es sich um eine schnelle und einfache Möglichkeit, eine COM-Komponente in C++ erstellen und verwalten einen geringen Ressourcenbedarf. Verwenden Sie ATL, um ein Steuerelement zu erstellen, wenn Sie alle integrierten Funktionen benötigen, die MFC automatisch bereitstellt.  
  
## <a name="using-mfc"></a>Verwenden von MFC  
 MFC bietet die Möglichkeit zum Erstellen von Anwendungen mit vollem, ActiveX-Steuerelemente und aktive Dokumente. Wenn Sie bereits ein Steuerelement mit MFC erstellt haben, empfiehlt es sich um Development in MFC zu fortfahren. Wenn Sie ein neues Steuerelement zu erstellen, sollten Sie mit ATL, wenn Sie alle MFC integrierte Funktionen benötigen.  
  
## <a name="using-atl-in-an-mfc-project"></a>Verwenden ATL in einem MFC-Projekt  
 Sie können Unterstützung für die Verwendung von ATL in einem vorhandenen MFC-Projekt mithilfe ein Assistenten hinzufügen. Weitere Informationen finden Sie unter [Hinzufügen von ATL-Unterstützung auf MFC-Projekt](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in ATL](../atl/introduction-to-atl.md)

