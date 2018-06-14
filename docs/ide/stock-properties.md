---
title: Basiseigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- stock properties, about stock properties
- stock properties
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3586fb33c30148c870b096d0d49a41d7ad8c6c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33335433"
---
# <a name="stock-properties"></a>Basiseigenschaften
Wenn Sie einer MFC-Disp-Schnittstelle mithilfe des [Assistenten zum Hinzufügen von Eigenschaften](../ide/idl-attributes-add-property-wizard.md) eine Eigenschaft hinzufügen, können Sie auf der [Namen](../ide/names-add-property-wizard.md)-Seite des Assistenten eine Basiseigenschaft aus der Liste **Eigenschaftennamen** auswählen. Dort stehen die folgenden Eigenschaften zur Auswahl:  
  
|Name der Eigenschaft|Beschreibung|  
|-------------------|-----------------|  
|**Darstellung**|Ruft einen Wert ab, der die Darstellung des Steuerelements bestimmt, oder legt diesen fest. Die Eigenschaft **Darstellung** des Steuerelements kann dreidimensionale Anzeigeeffekte anzeigen oder ausblenden. Dies ist eine Ambient-Lese-/Schreibeigenschaft.|  
|`BackColor`|Gibt die Ambient-Eigenschaft `BackColor` des Steuerelements zurück oder legt diese auf eine Palettenfarbe (RGB) oder eine vordefinierte Systemfarbe fest. Der Wert entspricht standardmäßig der Vordergrundfarbe des Containers des Steuerelements. Dies ist eine Ambient-Lese-/Schreibeigenschaft.|  
|`BorderStyle`|Gibt die Rahmenart eines Steuerelements zurück oder legt diese fest. Dies ist eine Lese-/Schreibeigenschaft.|  
|**Beschriftung**|Gibt die Eigenschaft **Beschriftung** des Steuerelements zurück oder legt diese fest. Die Beschriftung ist der Titel des Fensters. **Beschriftung** verfügt nicht über den Implementierungstyp **Membervariable**.|  
|**Aktiviert**|Gibt die Eigenschaft **Aktiviert** des Steuerelements zurück oder legt diese fest. Ein aktiviertes Steuerelement kann auf vom Benutzer generierte Ereignisse reagieren.|  
|**Schriftart**|Gibt die Ambient-Schriftart des Steuerelements zurück oder legt diese fest. Wenn das Steuerelement über keine Schriftart verfügt, wird NULL zurückgegeben.|  
|`ForeColor`|Gibt die Ambient-Eigenschaft `ForeColor` des Steuerelements zurück oder legt diese fest.|  
|**hWnd**|Gibt die **hWnd**-Eigenschaft des Steuerelements zurück oder legt diese fest. **hWnd** verfügt nicht über den Implementierungstyp **Membervariable**.|  
|**ReadyState**|Gibt die **ReadyState**-Eigenschaft des Steuerelements zurück oder legt diese fest. Ein Steuerelement kann folgenden Status aufweisen: nicht initialisiert, initialisiert, wird geladen, interaktiv und abgeschlossen. Weitere Informationen finden Sie unter [READYSTATE](https://msdn.microsoft.com/en-us/library/aa768362.aspx) im *Internet SDK*.|  
|**Text**|Gibt den Text zurück, der in einem Steuerelement enthalten ist, oder legt diesen fest. **Text** verfügt nicht über den Implementierungstyp **Membervariable**.|  
  
## <a name="see-also"></a>Siehe auch  
 [Adding a Property (Hinzufügen einer Eigenschaft)](../ide/adding-a-property-visual-cpp.md)   
 [IDL-Attribute, Assistent zum Hinzufügen von Eigenschaften](../ide/idl-attributes-add-property-wizard.md)