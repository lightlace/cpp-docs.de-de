---
title: "CAxDialogImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAxDialogImpl"
  - "ATL.CAxDialogImpl"
  - "CAxDialogImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Dialogfelder"
  - "CAxDialogImpl class"
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAxDialogImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert ein modales Dialogfeld \(oder nicht modale\) dieses Hosts ActiveX\-Steuerelemente.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class T,  
class TBase= CWindow  
>  
class ATL_NO_VTABLE CAxDialogImpl :  
public CDialogImplBaseT< TBase>  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `CAxDialogImpl`.  
  
 *TBase*  
 Bei der Fensterklasse für **CDialogImplBaseT**.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAxDialogImpl::AdviseSinkMap](../Topic/CAxDialogImpl::AdviseSinkMap.md)|Rufen Sie diese Methode auf, um alle Einträge in der Senken\-Zuordnungsereigniszuordnung des Objekts Anmeldung oder abzumelden.|  
|[CAxDialogImpl::Create](../Topic/CAxDialogImpl::Create.md)|Rufen Sie diese Methode auf, um ein nicht modales Dialogfeld zu erstellen.|  
|[CAxDialogImpl::DestroyWindow](../Topic/CAxDialogImpl::DestroyWindow.md)|Rufen Sie diese Methode auf, um ein nicht modales Dialogfeld zu zerstören.|  
|[CAxDialogImpl::DoModal](../Topic/CAxDialogImpl::DoModal.md)|Rufen Sie diese Methode auf, um ein modales Dialogfeld zu erstellen.|  
|[CAxDialogImpl::EndDialog](../Topic/CAxDialogImpl::EndDialog.md)|Rufen Sie diese Methode auf, um ein modales Dialogfeld zu zerstören.|  
|[CAxDialogImpl::GetDialogProc](../Topic/CAxDialogImpl::GetDialogProc.md)|Rufen Sie diese Methode auf, um einen Zeiger auf die `DialogProc` Rückruffunktion abzurufen.|  
|[CAxDialogImpl::GetIDD](../Topic/CAxDialogImpl::GetIDD.md)|Rufen Sie diese Methode auf, um die Dialogfeldvorlagenressourcen\-ID abzurufen|  
|[CAxDialogImpl::IsDialogMessage](../Topic/CAxDialogImpl::IsDialogMessage.md)|Rufen Sie diese Methode auf, um zu bestimmen, ob eine Meldung wird für dieses Dialogfeld vorgesehen und, wenn sie, dass die Meldung verarbeitet ist.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAxDialogImpl::m\_bModal](../Topic/CAxDialogImpl::m_bModal.md)|Eine Variable, die nur in Debugbuilds vorhanden und festgelegt wird, um auszurichten, wenn das Dialogfeld modal ist.|  
  
## Hinweise  
 `CAxDialogImpl` ermöglicht es Ihnen, ein modales oder ein nicht modales Dialogfeld zu erstellen.  `CAxDialogImpl` sieht die Dialogfeldprozedur vor, die die Standardmeldungszuordnung verwendet, um Meldungen auf die entsprechenden Handler zu verweisen.  
  
 `CAxDialogImpl` `CDialogImplBaseT` wird von abgeleitet, das wiederum *von TBase* \(standardmäßig, `CWindow`\) und von `CMessageMap` abgeleitet.  
  
 Die Klasse muss einen IDD\-Member definieren, der die ID Dialogfeldvorlagen\-Ressource angibt  Beispielsweise ein ATL\-Dialogfeld\-Objekt mithilfe des Dialogfelds hinzugefügt **Klasse hinzufügen** fügt automatisch die folgende Zeile der Klasse hinzu:  
  
 [!CODE [NVC_ATL_Windowing#41](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#41)]  
  
 wobei `MyDialog`**Kurzer Name** ist, das in den ATL\-Dialogfeld\-Assistenten eingegeben wird.  
  
 Siehe [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md) weitere Informationen.  
  
 Beachten Sie, dass ein ActiveX\-Steuerelement in einem modalen Dialogfeld, das mit `CAxDialogImpl` erstellt wird, nicht Zugriffstasten unterstützt.  Um Zugriffstasten in einem Dialogfeld zu unterstützen, das mit `CAxDialogImpl` erstellt wird, erstellen Sie ein nicht modales Dialogfeld und, mithilfe einer eigenen Meldungsschleife erstellt, verwenden Sie [CAxDialogImpl::IsDialogMessage](../Topic/CAxDialogImpl::IsDialogMessage.md) nachdem Sie eine Meldung aus der Warteschlange abgerufen wurde um eine Zugriffstaste zu behandeln.  
  
 Weitere Informationen zu `CAxDialogImpl`, finden Sie unter [ATL steuert Kapselung FAQs](../../atl/atl-control-containment-faq.md).  
  
## Vererbungshierarchie  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CDialogImplBaseT`  
  
 `CAxDialogImpl`  
  
## Anforderungen  
 **Header:**  atlwin.h  
  
## Siehe auch  
 [CDialogImpl Class](../../atl/reference/cdialogimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)