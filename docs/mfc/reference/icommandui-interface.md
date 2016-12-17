---
title: "ICommandUI Interface"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ICommandUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandUI interface"
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 24
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandUI Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet Benutzeroberflächenbefehle.  
  
## Syntax  
  
```  
interface class ICommandUI  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[ICommandUI::Check](../Topic/ICommandUI::Check.md)|Legt das Benutzeroberflächenelement für diesen Befehl zum entsprechenden Aktivierungszustand fest.|  
|[ICommandUI::ContinueRouting](../Topic/ICommandUI::ContinueRouting.md)|Weist den BefehlRouting Mechanismus mit, um das Weiterleiten der aktuellen Meldung in der Kette von Handlern fortzusetzen.|  
|[ICommandUI::Enabled](../Topic/ICommandUI::Enabled.md)|Aktiviert oder deaktiviert das Benutzeroberflächenelement für diesen Befehl.|  
|[ICommandUI::ID](../Topic/ICommandUI::ID.md)|Ruft die ID des Benutzeroberflächenobjekts ab, das vom `ICommandUI`\-Objekt dargestellt wird.|  
|[ICommandUI::Index](../Topic/ICommandUI::Index.md)|Ruft den Index des Benutzeroberflächenobjekts ab, das vom `ICommandUI`\-Objekt dargestellt wird.|  
|[ICommandUI::Radio](../Topic/ICommandUI::Radio.md)|Legt das Benutzeroberflächenelement für diesen Befehl zum entsprechenden Aktivierungszustand fest.|  
|[ICommandUI::Text](../Topic/ICommandUI::Text.md)|Legt den Text des Benutzeroberflächenelements für diesen Befehl fest.|  
  
## Hinweise  
 Diese Schnittstelle stellt Methoden und Eigenschaften, die Benutzeroberflächenbefehle verwalten.  `ICommandUI` ist zu [CCmdUI Class](../../mfc/reference/ccmdui-class.md) vergleichbar, außer dass `ICommandUI` wird für MFC\-Anwendungen verwendet, die mit .NET\-Komponenten zusammenarbeiten.  
  
 `ICommandUI` wird innerhalb eines `ON_UPDATE_COMMAND_UI`\-Handlers in [ICommandTarget](../../mfc/reference/icommandtarget-interface.md) von abgeleitete Klasse verwendet.  Wenn ein Benutzer einer Anwendung \(aktiviert oder klickt\), ein Menü aktiviert, wird jedes Menüelement angezeigt, wie aktiviert oder deaktiviert.  Das Ziel jedes Menübefehls stellt diese Informationen aus dem Implementieren eines Handlers `ON_UPDATE_COMMAND_UI` bereit.  Für jedes der Befehlsbenutzeroberflächenobjekte in der Anwendung, verwenden Sie das Eigenschaftenfenster, um einen Eintrag in der Meldungszuordnung und einen Funktionsprototyp für jeden Handler zu erstellen.  
  
 Weitere Informationen darüber, wie die `ICommandUI`\-Schnittstelle im Befehlsrouting verwendet wird, finden Sie unter [Gewusst wie: Hinzufügen von Befehlsrouting zum Windows Forms\-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Weitere Informationen zur Verwendung von Windows Forms, finden Sie unter [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Weitere Informationen dazu, wie Benutzeroberflächenbefehle in MFC verwaltet werden, finden Sie unter [CCmdUI Class](../../mfc/reference/ccmdui-class.md).  
  
## Anforderungen  
 **Header:** afxwinforms.h \(definiert in Assembly in \\ atlmfc \\ lib mfcmifc80.dll\)  
  
## Siehe auch  
 [CCmdUI Class](../../mfc/reference/ccmdui-class.md)