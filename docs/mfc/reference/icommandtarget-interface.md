---
title: ICommandTarget Schnittstelle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
dev_langs:
- C++
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be8adb388bed39f91637dd1ef37ee1ee895f291d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="icommandtarget-interface"></a>ICommandTarget-Schnittstelle
Bietet eine Schnittstelle zum Empfangen Befehle von einem Befehlsquellobjekt ein Benutzersteuerelement hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```  
interface class ICommandTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ICommandTarget:: Initialize](#initialize)|Initialisiert das Zielobjekt für den Befehl.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie ein benutzerdefiniertes Steuerelement in einer MFC-Ansicht hosten [CWinFormsView](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI Nachrichten auf das Benutzersteuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleisten-Schaltflächen) verarbeiten kann. Durch die Implementierung `ICommandTarget`, Sie geben dem Benutzersteuerelement einen Verweis auf die [ICommandSource](../../mfc/reference/icommandsource-interface.md) Objekt.  
  
 Finden Sie unter [wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `ICommandTarget`.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  
  
##  <a name="initialize"></a>ICommandTarget:: Initialize  
 Initialisiert das Zielobjekt für den Befehl.  
  
```  
void Initialize(ICommandSource^ cmdSource);  
```  
  
### <a name="parameters"></a>Parameter  
 `cmdSource`  
 Ein Handle für das Quellobjekt für den Befehl.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein benutzerdefiniertes Steuerelement im MFC-Ansicht hosten, leitet CWinFormsView Befehle und Update-befehlsmeldungen UI auf das Benutzersteuerelement zum Behandeln von MFC-Befehle zuzulassen.  
  
 Diese Methode initialisiert die Ziel-Befehlsobjekt und ordnet den angegebenen Befehl Quelle Objekt CmdSource. Es sollte in der Implementierung des Benutzersteuerelements Klasse aufgerufen werden. Bei der Initialisierung sollten Sie Befehlshandler für das Befehlsquellobjekt vom aufrufenden ICommandSource::AddCommandHandler in der Initialize-Implementierung registrieren. Finden Sie unter Vorgehensweise: Hinzufügen von Befehlsrouting an Windows Forms-Steuerelement für ein Beispiel zum Initialisieren zu diesem Zweck verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Hinzufügen (Befehl) Befehlsrouting zum Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandSource-Schnittstelle](../../mfc/reference/icommandsource-interface.md)



