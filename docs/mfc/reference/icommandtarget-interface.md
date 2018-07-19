---
title: ICommandTarget-Schnittstelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 086b0b1d17d32a747802a8c1df783fb6a20a560e
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339773"
---
# <a name="icommandtarget-interface"></a>ICommandTarget-Schnittstelle
Stellt ein Steuerelement mit einer Schnittstelle empfangen Befehle von einem Befehlsquellobjekt bereit.  
  
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
 Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI-Nachrichten an das Steuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleistenschaltflächen) verarbeiten kann. Durch die Implementierung `ICommandTarget`, geben Sie dem Benutzersteuerelement einen Verweis auf die [ICommandSource](../../mfc/reference/icommandsource-interface.md) Objekt.  
  
 Finden Sie unter [Vorgehensweise: Hinzufügen Befehlsrouting an der Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zur Verwendung für `ICommandTarget`.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  
  
##  <a name="initialize"></a> ICommandTarget:: Initialize  
 Initialisiert das Zielobjekt für den Befehl.  
  
```  
void Initialize(ICommandSource^ cmdSource);  
```  
  
### <a name="parameters"></a>Parameter  
 *cmdSource*  
 Ein Handle für das Befehlsquellobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, leitet CWinFormsView Befehle und UI-befehlsmeldungen Update auf das Benutzersteuerelement, damit Sie die MFC-Befehle verarbeiten kann.  
  
 Diese Methode das Zielobjekt für den Befehl initialisiert und verknüpft es mit den angegebenen Befehl Quelle Objekt CmdSource. Es sollte in der Implementierung der Benutzer Control-Klasse aufgerufen werden. Bei der Initialisierung sollten Sie mit das Befehlsquellobjekt vom aufrufenden ICommandSource::AddCommandHandler in der Initialize-Implementierung Befehlshandler registrieren. Finden Sie unter Vorgehensweise: Hinzufügen von Befehlsrouting für das Windows Forms-Steuerelement für ein Beispiel zum Initialisieren, die zu diesem Zweck verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Befehl "hinzufügen" Routing an das Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandSource-Schnittstelle](../../mfc/reference/icommandsource-interface.md)



