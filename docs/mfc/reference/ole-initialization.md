---
title: OLE-Initialisierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
dev_langs:
- C++
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 330701c4fcc75d40e782d25baa55044b88852f50
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337792"
---
# <a name="ole-initialization"></a>OLE-Initialisierung
Bevor eine Anwendung auf OLE-Systemdienste verwenden kann, müssen sie die OLE-System-DLLs initialisieren und stellen Sie sicher, dass die DLLs der richtigen Version vorliegen. Die `AfxOleInit` Funktion initialisiert die OLE-System-DLLs.  
  
### <a name="ole-initialization"></a>OLE-Initialisierung  
  
|||  
|-|-|  
|[AfxOleInit](#afxoleinit)|Initialisiert die OLE-Bibliotheken.| 
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Rufen Sie diese Funktion in Ihrem Anwendungsobjekt `InitInstance` Funktion, um Unterstützung für die Kapselung der OLE-Steuerelemente zu aktivieren.| 


## <a name="afxenablecontrolcontainer"></a> AfxEnableControlContainer
Rufen Sie diese Funktion in Ihrem Anwendungsobjekt `InitInstance` Funktion, um Unterstützung für die Kapselung der OLE-Steuerelemente zu aktivieren.  
   
### <a name="syntax"></a>Syntax    
```
void AfxEnableControlContainer( );  
```  
   
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu OLE-Steuerelemente (jetzt als ActiveX-Steuerelemente bezeichnet), finden Sie unter [ActiveX-Steuerelement Themen](../mfc-activex-controls.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  

  
##  <a name="afxoleinit"></a>  AfxOleInit  
 Initialisiert die OLE-Unterstützung für die Anwendung.  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist nicht 0 (Null), wenn erfolgreich, und 0, wenn die Initialisierung fehlschlägt, weil möglicherweise falsche Versionen der OLE-Systeme-DLLs installiert sind.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion auf, um die OLE-Unterstützung für eine MFC-Anwendung zu initialisieren. Wenn diese Funktion aufgerufen wird, werden folgende Aktionen ausgeführt:  
  
-   Initialisiert die COM-Bibliothek für das aktuelle Apartment des aufrufenden Anwendung. Weitere Informationen finden Sie unter [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134).  
  
-   Erstellt ein nachrichtenfilterobjekt und implementiert die [IMessageFilter](http://msdn.microsoft.com/library/windows/desktop/ms693740) Schnittstelle. Dieser Nachrichtenfilter kann zugegriffen werden, mit einem Aufruf von [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
> [!NOTE]
>  Wenn **AfxOleInit** heißt aus einer MFC-DLL der Aufruf schlägt fehl. Der Fehler tritt auf, weil die Funktion davon ausgeht, dass das OLE-System zuvor von der aufrufenden Anwendung initialisiert wurde, wenn sie von einer DLL aufgerufen wird.  
  
> [!NOTE]
>  MFC-Anwendungen müssen als Singlethread-Apartment (STA) initialisiert werden. Wenn Sie aufrufen [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) in Ihre `InitInstance` außer Kraft setzen, geben Sie COINIT_APARTMENTTHREADED (anstelle von COINIT_MULTITHREADED) an. Weitere Informationen finden Sie unter PRB: MFC-Anwendung nicht mehr reagiert, wenn Sie die Anwendung als eine Multithread-Apartment (828643) am initialisieren [ http://support.microsoft.com/default.aspxscid=kb; En-us; 828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
