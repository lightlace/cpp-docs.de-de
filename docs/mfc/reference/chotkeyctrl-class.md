---
title: "CHotKeyCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHotKeyCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHotKeyCtrl class"
  - "hot key controls"
  - "Windows common controls [C++], CHotKeyCtrl"
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CHotKeyCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des allgemeinen Abkürzungstasten\-Steuerelements Windows bereit.  
  
## Syntax  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](../Topic/CHotKeyCtrl::CHotKeyCtrl.md)|Erstellt ein `CHotKeyCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CHotKeyCtrl::Create](../Topic/CHotKeyCtrl::Create.md)|Erstellt ein und fügt es Abkürzungstasten\-Steuerelement zu einem `CHotKeyCtrl`\-Objekt.|  
|[CHotKeyCtrl::CreateEx](../Topic/CHotKeyCtrl::CreateEx.md)|Erstellt ein Abkürzungstasten\-Steuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CHotKeyCtrl`\-Objekt.|  
|[CHotKeyCtrl::GetHotKey](../Topic/CHotKeyCtrl::GetHotKey.md)|Ruft den virtuellen Tastencode und die Modifiziererflags einer Zugriffstaste von einem Abkürzungstasten\-Steuerelement ab.|  
|[CHotKeyCtrl::GetHotKeyName](../Topic/CHotKeyCtrl::GetHotKeyName.md)|Ruft den Schlüsselnamen, im lokalen Zeichensatz ab, zugewiesen einer Zugriffstaste.|  
|[CHotKeyCtrl::GetKeyName](../Topic/CHotKeyCtrl::GetKeyName.md)|Ruft den Schlüsselnamen, im lokalen Zeichensatz ab, dem angegebenen virtuellen Tastencode zugewiesen.|  
|[CHotKeyCtrl::SetHotKey](../Topic/CHotKeyCtrl::SetHotKey.md)|Legt die Abkürzungstastenkombination für ein Abkürzungstasten\-Steuerelement fest.|  
|[CHotKeyCtrl::SetRules](../Topic/CHotKeyCtrl::SetRules.md)|Definiert die ungültigen Kombinationen und die standardmäßige Modifiziererkombination für ein Abkürzungstasten\-Steuerelement.|  
  
## Hinweise  
 Ein "Abkürzungstasten\-Steuerelement" ist ein Fenster, das den Benutzer ermöglicht, eine Zugriffstaste zu erstellen.  Eine "Abkürzungstaste\-Steuerelement" ist eine Tastenkombination, die der Benutzer klicken kann, um eine Aktion schnell auszuführen.  \(beispielsweise, kann ein Benutzer eine Zugriffstaste erstellen, die einem angegebenen Fenster aktiviert und der Rand der z\-Ordnung führt\). Das Abkürzungstasten\-Steuerelement zeigt die Auswahl des Benutzers an und stellt sicher, dass der Benutzer eine gültige Tastenkombination auswählt.  
  
 Dieses Steuerelement \(und daher die `CHotKeyCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT 3,51 und höher ausgeführt werden.  
  
 Wenn der Benutzer eine Tastenkombination ausgewählt hat, kann die Anwendung die Kombination des angegebenen Schlüssels vom Steuerelement abrufen und die **WM\_SETHOTKEY** Meldung verwenden, um die Zugriffstaste im System zu installieren.  Sobald der Benutzer drückt, empfängt die Zugriffstaste später, von Teilen des Systems, das Fenster, das in der **WM\_SETHOTKEY** Meldung angegeben wird, eine `WM_SYSCOMMAND` Meldung **SC\_HOTKEY** angibt.  Diese Meldung kann das Fenster, das empfängt.  Die Abkürzungstaste\-Steuerelement bleibt gültig, bis die Anwendung die **WM\_SETHOTKEY** beendet hat.  
  
 Dieser Mechanismus ist mit der Abkürzungstastenunterstützung unterscheiden, die von der **WM\_HOTKEY** Meldung und von Funktionen Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) und [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) abhängt.  
  
 Weitere Informationen zur Verwendung von `CHotKeyCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)