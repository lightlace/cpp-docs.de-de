---
title: "ASP, ATL-Assistent für Active Server Page-Komponenten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.asp.asp
dev_langs:
- C++
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69d3837cc0996c0e0e0784214cfbfa6744afbf94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP, ATL-Assistent für Active Server Page-Komponenten
Mit der optionale Einstellungen angeben, für die Behandlung von Informationen und Status, die im Zusammenhang mit der ASP-Komponente auf dieser Seite des ATL-Assistenten für Active Server Page-Komponente.  
  
 **Optionale Methoden**  
 Fügt die optionalen ASP-Methoden **OnStartPage** und **OnEndPage**, für Ihr Objekt. Diese Option muss ausgewählt werden, alle systeminternen Objekten von Active Server Pages festlegen. Es ist standardmäßig ausgewählt.  
  
-   **OnStartPage/OnEndPage** [OnStartPage](https://msdn.microsoft.com/library/ms691624.aspx) zum ersten Mal das Skript versucht, auf das Objekt aufgerufen wird. **OnEndPage** wird aufgerufen, wenn das Objekt beendet, wird das Skript zu verarbeiten.  
  
 **Systeminterne Objekt**  
 Wählen Sie die **OnStartPage/OnEndPage** Option aus, um alle ASP-Objekte festgelegt.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Anforderung**|Bietet Zugriff auf die systeminterne Funktion der Active Server Pages **anfordern** Objekt. Das Request-Objekt wird verwendet, um eine HTTP-Anforderung übergeben.|  
|**Antwort**|Bietet Zugriff auf die systeminterne Funktion der Active Server Pages **Antwort** Objekt. Als Antwort auf eine Anforderung sendet das Antwortobjekt Informationen an den Browser, den Benutzer angezeigt.|  
|**Sitzung**|Bietet Zugriff auf die systeminterne Funktion der Active Server Pages **Sitzung** Objekt. Die **Sitzung** Objekt enthält Informationen über die aktuelle benutzersitzung, z. B. speichern und Abrufen von Statusinformationen.|  
|**Anwendung**|Bietet Zugriff auf die systeminterne Funktion der Active Server Pages **Anwendung** Objekt. Die **Anwendung** Objekt verwaltet den Zustand, die für mehrere ASP-Objekte freigegeben wird.|  
|**Server**|Bietet Zugriff auf die systeminterne Funktion der Active Server Pages **Server** Objekt. Die **Server** Objekts können Sie zum Erstellen anderer ASP-Objekte.|  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Assistent für Active Server Page-Komponenten](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page-Komponenten](../../atl/reference/adding-an-atl-active-server-page-component.md)

