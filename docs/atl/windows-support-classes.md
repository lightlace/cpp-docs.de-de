---
title: Windows-Unterstützungsklassen (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.windows
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2095e5141dfdd320bae0e7aa69ffd4b3c9fe9a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362081"
---
# <a name="windows-support-classes"></a>Windows-Unterstützungsklassen
Die folgenden Klassen bieten Unterstützung für Windows:  
  
-   [_U_MENUorID](../atl/reference/u-menuorid-class.md) stellt Wrapper für **CreateWindow** und **CreateWindowEx**.  
  
-   [CWindow](../atl/reference/cwindow-class.md) enthält Methoden zum Bearbeiten eines Fensters. `CWindow` ist die Basisklasse für `CWindowImpl`, `CDialogImpl` und `CContainedWindow`.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) implementiert ein Fenster, die basierend auf einem neuen Fensterklasse. Außerdem ermöglicht Ihnen das Unterklasse oder übergeordneten Fenster.  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md) ein Dialogfeld implementiert.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) implementiert ein Dialogfeld (gebunden oder ungebunden), die ActiveX-Steuerelemente hostet.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) ein Dialogfeld (gebunden oder ungebunden) mit grundlegenden Funktionen implementiert.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) bearbeitet ein Fenster, das ein ActiveX-Steuerelement hostet.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) bietet Methoden zum Bearbeiten von ein Fenster, das ein ActiveX-Steuerelement gehostet und bietet auch Unterstützung für das lizenzierten ActiveX-Steuerelemente hosten.  
  
-   [CContainedWindow](../atl/reference/ccontainedwindowt-class.md) implementiert ein Fenster innerhalb eines anderen Objekts enthalten.  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) verwaltet die Informationen in eine neue Windows-Klasse.  
  
-   [CDynamicChain](../atl/reference/cdynamicchain-class.md) unterstützt dynamische Verkettung von meldungszuordnungen.  
  
-   [CMessageMap](../atl/reference/cmessagemap-class.md) ermöglicht, die ein Objekt, dessen Meldung verfügbar zu machen, die auf andere Objekte zugeordnet wird.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) bietet eine einfache Methode zum Standardisieren die Merkmale eines ATL-Fenster-Objekts.  
  
-   [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) gibt Standardwerte für Fensterstile und erweiterte Formate, die beim Erstellen eines Fensters verwendet. Diese Werte werden hinzugefügt und mithilfe des logischen OR-Operators auf Werte, die während der Erstellung eines Fensters bereitgestellt.  
  
## <a name="related-articles"></a>Verwandte Artikel  
 [ATL-Fensterklassen](../atl/atl-window-classes.md)  
  
 [ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../atl/atl-class-overview.md)   
 [Meldungszuordnungsmakros](../atl/reference/message-map-macros-atl.md)   
 [Fensterklassen-Makros](../atl/reference/window-class-macros.md)

