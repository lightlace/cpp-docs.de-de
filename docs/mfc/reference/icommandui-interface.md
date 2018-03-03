---
title: ICommandUI Schnittstelle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
dev_langs:
- C++
helpviewer_keywords:
- ICommandUI interface [MFC]
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4971ceaea57b91ff708315a2c32c7bac2801798f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="icommandui-interface"></a>ICommandUI-Schnittstelle
Verwaltet von Befehlen der Benutzeroberfläche.  
  
## <a name="syntax"></a>Syntax  
  
```  
interface class ICommandUI  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[icommandui__Check](#check)|Legt die Benutzer-Schnittstelle-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.|  
|[ICommandUI::ContinueRouting](#continuerouting)|Weist den Mechanismus Befehlsrouting Weiterleiten der aktuellen Nachricht unten die Kette der Handler fortgesetzt.|  
|[ICommandUI::Enabled](#enabled)|Aktiviert oder deaktiviert die Benutzer-Schnittstelle-Element für diesen Befehl.|  
|[ICommandUI::ID](#id)|Ruft die ID des Benutzerobjekts für die Schnittstelle dargestellt, die durch die `ICommandUI` Objekt.|  
|[ICommandUI::Index](#index)|Ruft den Index des dem Benutzer-Schnittstellenobjekt, dargestellt durch die `ICommandUI` Objekt.|  
|[ICommandUI::Radio](#radio)|Legt die Benutzer-Schnittstelle-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.|  
|[ICommandUI::Text](#text)|Legt den Text des Elements Schnittstelle Benutzer für diesen Befehl fest.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle bietet Methoden und Eigenschaften, die Befehlen der Benutzeroberfläche verwalten. `ICommandUI`ähnelt dem [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md), außer dass `ICommandUI` für MFC-Anwendungen, die mit Visual Studio .NET Komponenten Zusammenwirken verwendet.  
  
 `ICommandUI`wird verwendet, in ein `ON_UPDATE_COMMAND_UI` Ereignishandler in einem [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-abgeleitete Klasse. Wenn ein Benutzer einer Anwendung (SELECT-Anweisungen oder Klicks) aktiviert wird ein Menü, jede Menüelement angezeigt, als aktiviert oder deaktiviert. Das Ziel jeder Menübefehl stellt diese Informationen durch die Implementierung einer `ON_UPDATE_COMMAND_UI` Handler. Verwenden Sie für jeden Befehl Schnittstelle Benutzerobjekte in der Anwendung des Eigenschaftenfensters zum Erstellen einer Meldungszuordnungseintrags und Funktionsprototyp für jeden Handler.  
  
 Weitere Informationen darüber, wie der `ICommandUI` Schnittstelle in Befehlsrouting verwendet wird, finden Sie unter [wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Weitere Informationen wie Benutzeroberflächenbefehlen in MFC verwaltet werden, finden Sie unter [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md).  
  
## <a name="check"></a>ICommandUI::Check  
Legt die Benutzer-Schnittstelle-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.
```
property UICheckState Check;
```
## <a name="remarks"></a>Hinweise  
Diese Eigenschaft legt die Benutzer-Schnittstelle-Element für diesen Befehl auf den entsprechenden Aktivierungszustand an. Überprüfen Sie auf die folgenden Werte festgelegt:  
- 0 deaktivieren Sie  
- 1 Überprüfen  
- Legen Sie unbestimmt 2  

## <a name="continuerouting"></a>ICommandUI::ContinueRouting   
Weist den Befehl Routingmechanismus dar, um den Vorgang fortzusetzen, routing von der aktuellen Nachricht unten die Kette der Handler.
```
void ContinueRouting();
```
## <a name="remarks"></a>Hinweise
Dies ist eine erweiterte Memberfunktion, die in Verbindung mit einer ON_COMMAND_EX-Handler verwendet werden soll, die "false" zurückgibt. Weitere Informationen finden Sie im technischen Hinweis TN006: Meldungszuordnungen.

## <a name="enabled"></a>ICommandUI::Enabled 
Aktiviert oder deaktiviert die Benutzer-Schnittstelle-Element für diesen Befehl.
```
property bool Enabled;
```
## <a name="remarks"></a>Hinweise
Diese Eigenschaft aktiviert oder deaktiviert die Benutzer-Schnittstelle-Element für diesen Befehl. Legen Sie aktiviert, um "true" aktiviert das Element "false", um ihn zu deaktivieren.

## <a name="id"></a>ICommandUI::ID  
Ruft die ID des Benutzerobjekts für die Schnittstelle vom ICommandUI Objekt dargestellt wird.
```
property unsigned int ID;
```
## <a name="remarks"></a>Hinweise
Diese Eigenschaft ruft die ID (ein Handle) des Menüelements, Symbolleisten-Schaltfläche oder andere Benutzeroberflächen-Objekt, das vom ICommandUI-Objekt dargestellt wird.

## <a name="index"></a>ICommandUI::Index   
Ruft den Index des Benutzerobjekts für die Schnittstelle vom ICommandUI Objekt dargestellt wird.
```
property unsigned int Index;
```
## <a name="remarks"></a>Hinweise
Diese Eigenschaft ruft den Index (ein Handle) des Menüelements, Symbolleisten-Schaltfläche oder andere Benutzeroberflächen-Objekt, das vom ICommandUI-Objekt dargestellt wird.

## <a name="radio"></a>ICommandUI::Radio 
Legt die Benutzer-Schnittstelle-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.
```
property bool Radio;
```
## <a name="remarks"></a>Hinweise
Diese Eigenschaft legt die Benutzer-Schnittstelle-Element für diesen Befehl auf den entsprechenden Aktivierungszustand an. Festlegen der Sender auf "true" aktiviert das Element; andernfalls "false".

## <a name="text"></a>ICommandUI::Text 
Legt den Text des Elements Schnittstelle Benutzer für diesen Befehl fest.
```
property String^ Text;
```
## <a name="remarks"></a>Hinweise
Diese Eigenschaft legt den Text des Elements Schnittstelle Benutzer für diesen Befehl fest. Legen Sie Text an ein Text-Zeichenfolge-Handle.

## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md)
