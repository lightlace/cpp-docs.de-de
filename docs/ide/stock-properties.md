---
title: "Basiseigenschaften | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Basiseigenschaften"
  - "Basiseigenschaften, Informationen über Basiseigenschaften"
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Basiseigenschaften
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie einer MFC\-Dispatchschnittstelle  mithilfe des [Assistenten zum Hinzufügen von Eigenschaften](../ide/idl-attributes-add-property-wizard.md) eine Eigenschaft hinzufügen, können Sie im Assistenten auf der Seite [Namen](../ide/names-add-property-wizard.md) aus der Liste **Eigenschaftenname** eine Basiseigenschaft auswählen.  Dort stehen die folgenden Eigenschaften zur Auswahl:  
  
|Eigenschaftenname|Beschreibung|  
|-----------------------|------------------|  
|**Darstellung**|Gibt einen Wert zurück, der die Darstellung des Steuerelements bestimmt, oder legt diesen fest.  Die Eigenschaft **Darstellung** des Steuerelements kann dreidimensionale Anzeigeeffekte umfassen oder nicht.  Es handelt sich um eine **Ambient**\-Eigenschaft mit Lese\-\/Schreibzugriff.|  
|`BackColor`|Gibt die **Ambient**\-Eigenschaft `BackColor` des Steuerelements zurück oder legt für diese Eigenschaft entweder eine Palettenfarbe \(RGB\) oder eine vordefinierte Systemfarbe fest.  Standardmäßig entspricht dieser Wert der Vordergrundfarbe des Steuerelementcontainers.  Es handelt sich um eine **Ambient**\-Eigenschaft mit Lese\-\/Schreibzugriff.|  
|`BorderStyle`|Gibt die Rahmenart für ein Steuerelement zurück oder legt diese fest.  Dies ist eine Eigenschaft mit Lese\-\/Schreibzugriff.|  
|**Beschriftung**|Gibt die **Caption**\-Eigenschaft des Steuerelements zurück oder legt diese fest.  Die Beschriftung entspricht dem Fenstertitel.  Der Implementierungstyp **Membervariable** ist für **Capiton** nicht verfügbar.|  
|**Aktiviert**|Gibt die **Enabled**\-Eigenschaft des Steuerelements zurück oder legt diese fest.  Ein aktiviertes Steuerelement kann auf von Benutzern erstellte Ereignisse reagieren.|  
|**Schriftart**|Gibt die **Ambient**\-Eigenschaft **Font** des Steuerelements zurück oder legt diese fest.  **NULL**, falls das Steuerelement keine Schriftart besitzt.|  
|`ForeColor`|Gibt die **Ambient**\-Eigenschaft `ForeColor` des Steuerelements zurück oder legt diese fest.|  
|**hWnd**|Gibt die **hWnd**\-Eigenschaft des Steuerelements zurück oder legt diese fest.  **hWnd** verfügt nicht über den Implementierungstyp **Membervariable**.|  
|**ReadyState**|Gibt die **ReadyState**\-Eigenschaft des Steuerelements zurück oder legt diese fest.  Ein Steuerelement kann initialisiert, nicht initialisiert, interaktiv, abgeschlossen sein oder geladen werden.  Weitere Informationen finden Sie im *Internet\-SDK* unter [READYSTATE](https://msdn.microsoft.com/en-us/library/aa768362.aspx).|  
|**Text**|Gibt in einem Steuerelement enthaltenen Text zurück oder legt diesen fest.  Der Implementierungstyp **Membervariable** ist für **Text** nicht verfügbar.|  
  
## Siehe auch  
 [Hinzufügen einer Eigenschaft](../ide/adding-a-property-visual-cpp.md)   
 [IDL\-Attribute, Assistent zum Hinzufügen von Eigenschaften](../ide/idl-attributes-add-property-wizard.md)