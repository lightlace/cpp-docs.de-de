---
title: Vordefinierte Eigenschaften | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- stock properties, about stock properties
- stock properties
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9bbc721669d51860c01c760a8d1f9fb899e019e3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="stock-properties"></a>Basiseigenschaften
Wenn Sie eine Eigenschaft mit einem MFC-Dispinterface Hinzufügen der [Assistent zum Hinzufügen von Eigenschaften](../ide/idl-attributes-add-property-wizard.md), können Sie eine Systemeigenschaft aus der **Eigenschaftsname** in Liste der [Namen](../ide/names-add-property-wizard.md) auf der Seite der Assistenten. Dort stehen die folgenden Eigenschaften zur Auswahl:  
  
|Name der Eigenschaft|Beschreibung|  
|-------------------|-----------------|  
|**Darstellung**|Gibt an, oder legt einen Wert, der bestimmt, die Darstellung des Steuerelements fest. Des Steuerelements **Darstellung** Eigenschaft eingeschlossen oder weglassen von dreidimensionale Anzeigeeffekte kann. Dies ist eine ambient Lese-Schreib-Eigenschaft.|  
|`BackColor`|Gibt zurück, oder legt des Steuerelements ambient `BackColor` Eigenschaft, um eine (RGB)-Palettenfarbe oder eine vordefinierte Systemfarbe. Standardmäßig entspricht dieser Wert die Vordergrundfarbe des Containers des Steuerelements. Dies ist eine ambient Lese-Schreib-Eigenschaft.|  
|`BorderStyle`|Gibt an, oder legt die Rahmenart für ein Steuerelement. Dies ist eine Schreib-Lese-Eigenschaft.|  
|**Beschriftung**|Gibt zurück, oder legt das Steuerelement **Beschriftung** Eigenschaft. Die Beschriftung ist der Titel des Fensters. **Beschriftung** hat keine **Membervariable** Implementierungstyp.|  
|**Aktiviert**|Gibt zurück, oder legt das Steuerelement **aktiviert** Eigenschaft. Ein aktiviertes Steuerelement kann auf vom Benutzer generierte Ereignisse reagieren.|  
|**Schriftart**|Gibt zurück, oder legt ihn fest Ambiente-Schriftart des Steuerelements. NULL, wenn das Steuerelement keine Schriftart besitzt.|  
|`ForeColor`|Gibt zurück, oder legt des Steuerelements ambient `ForeColor` Eigenschaft.|  
|**hWnd**|Gibt zurück, oder legt das Steuerelement **hWnd** Eigenschaft. **hWnd** hat keine **Membervariable** Implementierungstyp.|  
|**ReadyState**|Gibt zurück, oder legt das Steuerelement **ReadyState** Eigenschaft. Ein Steuerelement kann nicht initialisiert, initialisiert, das Laden, interaktiven oder abgeschlossen sein. Finden Sie unter [READYSTATE](https://msdn.microsoft.com/en-us/library/aa768362.aspx) in der *Internet SDK* für Weitere Informationen.|  
|**Text**|Gibt an, oder legt den Text in einem Steuerelement enthalten. **Text** hat keine **Membervariable** Implementierungstyp.|  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer Eigenschaft](../ide/adding-a-property-visual-cpp.md)   
 [IDL-Attribute, Assistent zum Hinzufügen von Eigenschaften](../ide/idl-attributes-add-property-wizard.md)