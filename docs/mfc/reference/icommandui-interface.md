---
title: ICommandUI Schnittstelle | Microsoft-Dokumentation
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
- ICommandUI interface
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1db6b3fa58639140322816c37103566353b15633
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="icommandui-interface"></a>ICommandUI-Schnittstelle
Verwaltet von Befehlen der Benutzeroberfläche.  
  
## <a name="syntax"></a>Syntax  
  
```  
interface class ICommandUI  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[icommandui__Check](#check)|Legt die Benutzer-Interface-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.|  
|[ICommandUI::ContinueRouting](#continuerouting)|Teilt Befehlsrouting Mechanismus für die Weiterleitung der aktuellen Nachricht der Vererbungskette Handler fortgesetzt.|  
|[ICommandUI::Enabled](#enabled)|Aktiviert oder deaktiviert die Benutzer-Interface-Element für diesen Befehl.|  
|[ICommandUI::ID](#id)|Ruft die ID des das Benutzeroberflächenobjekt, dargestellt durch die `ICommandUI` Objekt.|  
|[ICommandUI::Index](#index)|Ruft den Index des das Benutzeroberflächenobjekt, dargestellt durch die `ICommandUI` Objekt.|  
|[ICommandUI::Radio](#radio)|Legt die Benutzer-Interface-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.|  
|[ICommandUI::Text](#text)|Legt den Text des Elements Schnittstelle Benutzer für diesen Befehl.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle stellt Methoden und Eigenschaften, die von Befehlen der Benutzeroberfläche verwalten. `ICommandUI`ähnelt dem [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md), außer dass `ICommandUI` für MFC-Anwendung, die mit .NET Komponenten Zusammenwirken verwendet wird.  
  
 `ICommandUI`wird verwendet, in ein `ON_UPDATE_COMMAND_UI` -Handler in einer [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-abgeleiteten Klasse. Wenn ein Benutzer einer Anwendung (aktiviert oder Klicks) aktiviert wird ein Menü, jedes Menüelement angezeigt, als aktiviert oder deaktiviert. Das Ziel der einzelnen Menübefehle bietet diese Informationen durch die Implementierung einer `ON_UPDATE_COMMAND_UI` Handler. Verwenden Sie für jeden Befehl Schnittstelle Benutzerobjekte in Ihrer Anwendung das Eigenschaftenfenster Meldungszuordnungseintrags und Funktionsprototyp für jeden Handler erstellen.  
  
 Weitere Informationen darüber, wie der `ICommandUI` Schnittstelle in Befehlsrouting verwendet wird, finden Sie unter [Gewusst wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Weitere Informationen dazu, wie Benutzeroberflächenbefehlen in MFC verwaltet werden, finden Sie unter [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md).  
  
## <a name="check"></a>ICommandUI::Check  
Legt die Benutzer-Interface-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.
```
property UICheckState Check;
```
## <a name="remarks"></a>Hinweise  
Diese Eigenschaft legt die Benutzer-Interface-Element für diesen Befehl an den entsprechenden Aktivierungszustand. Kontrollkästchen auf der folgenden Werte festgelegt:  
- 0 deaktivieren  
- 1 Überprüfen  
- Legen Sie unbestimmt&2;  

## <a name="continuerouting"></a>ICommandUI::ContinueRouting   
Weist den Befehl Weiterleitungsmechanismus routing der aktuellen Nachricht der Vererbungskette Handler fortgesetzt.
```
void ContinueRouting();
```
## <a name="remarks"></a>Hinweise
Dies ist ein erweiterter Member-Funktion, die in Verbindung mit einem Ereignishandler ON_COMMAND_EX verwendet werden soll, die FALSE zurückgibt. Weitere Informationen finden Sie unter Technische Hinweis TN006: Meldungszuordnungen.

## <a name="enabled"></a>ICommandUI::Enabled 
Aktiviert oder deaktiviert die Benutzer-Interface-Element für diesen Befehl.
```
property bool Enabled;
```
## <a name="remarks"></a>Hinweise
Diese Eigenschaft aktiviert bzw. deaktiviert das User Interface-Element für diesen Befehl. Legen Sie aktiviert, um "true" aktiviert das Element "false", um es zu deaktivieren.

## <a name="id"></a>ICommandUI::ID  
Ruft die ID des Benutzerobjekts für die Schnittstelle durch das ICommandUI-Objekt dargestellt wird.
```
property unsigned int ID;
```
## <a name="remarks"></a>Hinweise
Diese Eigenschaft ruft die ID (ein Handle) des Menüelements, Symbolleisten-Schaltfläche oder andere Benutzeroberflächen-Objekt, das vom ICommandUI-Objekt dargestellt.

## <a name="index"></a>ICommandUI::Index   
Ruft den Index des Benutzerobjekts für die Schnittstelle durch das ICommandUI-Objekt dargestellt wird.
```
property unsigned int Index;
```
## <a name="remarks"></a>Hinweise
Diese Eigenschaft ruft den Index (ein Handle) des Menüelements, Symbolleisten-Schaltfläche oder andere Benutzeroberflächen-Objekt, das vom ICommandUI-Objekt dargestellt.

## <a name="radio"></a>ICommandUI::Radio 
Legt die Benutzer-Interface-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.
```
property bool Radio;
```
## <a name="remarks"></a>Hinweise
Diese Eigenschaft legt die Benutzer-Interface-Element für diesen Befehl an den entsprechenden Aktivierungszustand. Legen Sie "true" aktiviert das Element Sender, um. andernfalls FALSE.

## <a name="text"></a>ICommandUI::Text 
Legt den Text des Elements Schnittstelle Benutzer für diesen Befehl.
```
property String^ Text;
```
## <a name="remarks"></a>Hinweise
Diese Eigenschaft legt den Text des Elements Schnittstelle Benutzer für diesen Befehl. Legen Sie Text mit einem Text-Zeichenfolge-Handle.

## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md)

