---
title: "CDialogImpl Class"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CDialogImpl"
  - "ATL.CDialogImpl"
  - "ATL::CDialogImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogImpl class"
  - "Dialogfelder, ATL"
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
caps.latest.revision: 25
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CDialogImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Erstellen ein modales oder ein nicht modales Dialogfeld bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class T,  
class TBase= CWindow   
>  
class ATL_NO_VTABLE CDialogImpl :  
public CDialogImplBaseT< TBase>  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `CDialogImpl`.  
  
 *TBase*  
 Die Basisklasse der neuen Klasse.  Die standardmäßige Basisklasse ist [CWindow](../../atl/reference/cwindow-class.md).  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[Create](../Topic/CDialogImpl::Create.md)|Stellt ein nicht modales Dialogfeld erstellt.|  
|[DestroyWindow](../Topic/CDialogImpl::DestroyWindow.md)|Zerstört ein nicht modales Dialogfeld.|  
|[DoModal](../Topic/CDialogImpl::DoModal.md)|Stellt ein modales Dialogfeld erstellt.|  
|[EndDialog](../Topic/CDialogImpl::EndDialog.md)|Zerstört ein modales Dialogfeld.|  
  
### CDialogImplBaseT\-Methoden  
  
|||  
|-|-|  
|[GetDialogProc](../Topic/CDialogImpl::GetDialogProc.md)|Gibt die aktuelle Dialogfeldprozedur zurück.|  
|[MapDialogRect](../Topic/CDialogImpl::MapDialogRect.md)|Ordnet die Dialogeinheiten des angegebenen Rechtecks zu, um Einheiten \(Pixel\) zu stößt.|  
|[OnFinalMessage](../Topic/CDialogImpl::OnFinalMessage.md)|Aufgerufen, nachdem die letzte Meldung, in der Regel `WM_NCDESTROY` empfangen wurde.|  
  
### Statische Funktionen  
  
|||  
|-|-|  
|[DialogProc](../Topic/CDialogImpl::DialogProc.md)|Verarbeitet die Meldungen, die dem Dialogfeld gesendet werden.|  
|[StartDialogProc](../Topic/CDialogImpl::StartDialogProc.md)|Aufgerufen, wenn die erste Nachricht empfangen wird, um die Nachrichten zu verarbeiten, die dem Dialogfeld gesendet werden.|  
  
## Hinweise  
 Mit `CDialogImpl` können Sie ein modales oder ein nicht modales Dialogfeld erstellen.  `CDialogImpl` sieht die Dialogfeldprozedur vor, die die Standardmeldungszuordnung verwendet, um Meldungen auf die entsprechenden Handler zu verweisen.  
  
 Der Basisklassendestruktor **~CWindowImplRoot** wird sichergestellt, dass das Fenster gegangen ist, bevor das Objekt zerstört.  
  
 `CDialogImpl` **CDialogImplBaseT** wird von abgeleitet, das wiederum von abgeleitet **CWindowImplRoot**.  
  
> [!NOTE]
>  Die Klasse muss einen **IDD**\-Member definieren, der die ID Dialogfeldvorlagen\-Ressource angibt  Beispielsweise fügt der ATL\-Projekt\-Assistent automatisch die folgende Zeile der Klasse hinzu:  
  
 [!CODE [NVC_ATL_Windowing#41](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#41)]  
  
 wobei `MyDlg`**Kurzer Name** ist, das in die Seite **Namen** des Assistenten eingegeben wird.  
  
|Weitere Informationen finden Sie unter|Siehe|  
|--------------------------------------------|-----------|  
|Erstellen von Steuerelementen|[ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md)|  
|Verwenden der Dialogfelder in ATL|[ATL\-Fensterklassen](../../atl/atl-window-classes.md)|  
|ATL\-Projekt\-Assistent|[Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)|  
|Dialogfelder|[Dialogfelder](http://msdn.microsoft.com/library/windows/desktop/ms632588) und folgende Themen in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## Anforderungen  
 **Header:**  atlwin.h  
  
## Siehe auch  
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)