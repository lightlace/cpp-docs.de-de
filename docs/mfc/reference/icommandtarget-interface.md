---
title: "ICommandTarget-Schnittstelle"
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
  - "ICommandTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandTarget-Schnittstelle"
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
caps.latest.revision: 27
caps.handback.revision: "27"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandTarget-Schnittstelle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt ein Benutzersteuerelement mit einer Schnittstelle zum Empfangen von Befehlen aus einem Befehlsquellobjekt bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
interface class ICommandTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ICommandTarget:: Initialize](#icommandtarget__initialize)|Initialisiert das Zielobjekt für den Befehl.|  
  
## <a name="remarks"></a>Hinweise  
 Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI-Nachrichten auf das Benutzersteuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleisten-Schaltflächen) verarbeiten kann. Durch die Implementierung `ICommandTarget`, geben Sie dem Benutzersteuerelement einen Verweis auf die [ICommandSource](../../mfc/reference/icommandsource-interface.md) Objekt.  
  
 Finden Sie unter [Gewusst wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `ICommandTarget`.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  
  
##  <a name="a-nameicommandtargetinitializea-icommandtargetinitialize"></a><a name="icommandtarget__initialize"></a> ICommandTarget:: Initialize  
 Initialisiert das Zielobjekt für den Befehl.  
  
```  
void Initialize(ICommandSource^ cmdSource);

 
```  
  
### <a name="parameters"></a>Parameter  
 `cmdSource`  
 Ein Handle für das Befehlsquellobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, leitet CWinFormsView Befehle und Update-Befehl UI Nachrichten auf das Benutzersteuerelement, damit Sie die MFC-Befehle zu verarbeiten kann.  
  
 Diese Methode initialisiert die Ziel-Befehlsobjekt und ordnet diese der angegebenen Quelle Objekt CmdSource. Es sollte in die Implementierung des Benutzersteuerelements Klasse aufgerufen werden. Bei der Initialisierung sollten Sie das Befehlsquellobjekt durch Aufrufen von ICommandSource::AddCommandHandler in der Initialize-Implementierung Befehlshandler registrieren. Finden Sie unter Gewusst wie: Hinzufügen von Befehlsrouting an die Windows Forms-Steuerelement ein Beispiel zum Initialisieren, die zu diesem Zweck verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Hinzufügen von Befehl Befehlsrouting zum Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandSource-Schnittstelle](../../mfc/reference/icommandsource-interface.md)



