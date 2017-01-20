---
title: "CDHtmlDialog Class"
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
  - "CDHtmlDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDHtmlDialog class"
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
caps.latest.revision: 23
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CDHtmlDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der wird verwendet, um Dialogfelder, die HTML, sondern als verwenden Dialogfeldressourcen erstellen, um die Benutzeroberfläche zu implementieren.  
  
## Syntax  
  
```  
class CDHtmlDialog : public CDialog, public CDHtmlEventSink  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDHtmlDialog::CDHtmlDialog](../Topic/CDHtmlDialog::CDHtmlDialog.md)|Erstellt ein CDHtmlDialog\-Objekt.|  
|[CDHtmlDialog::~CDHtmlDialog](../Topic/CDHtmlDialog::~CDHtmlDialog.md)|Zerstört ein CDHtmlDialog\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDHtmlDialog::CanAccessExternal](../Topic/CDHtmlDialog::CanAccessExternal.md)|Überschreibbar, das als Zugangsprüfung aufgerufen wird, um festzustellen, ob Skriptobjekte geladenen auf der Seite auf den externen Dispatch der Steuerungssite zugreifen können.  Die überprüft, um sich zu vergewissern Dispatchs des ist entweder safe für die Skripterstellung, oder die aktuelle Zone können Objekte zu, die nicht für die Skripterstellung sicher sind.|  
|[CDHtmlDialog::CreateControlSite](../Topic/CDHtmlDialog::CreateControlSite.md)|Überschreibbares verwendete, um eine Steuerungssiteinstanz erstellen, um das ActiveX\-Steuerelement browsersteuerelement im Dialogfeld zu hosten.|  
|[CDHtmlDialog::DDX\_DHtml\_AxControl](../Topic/CDHtmlDialog::DDX_DHtml_AxControl.md)|Austauschdaten zwischen einer Membervariablen und dem Eigenschaftswert eines ActiveX\-Steuerelements auf einer HTML\-Seite.|  
|[CDHtmlDialog::DDX\_DHtml\_CheckBox](../Topic/CDHtmlDialog::DDX_DHtml_CheckBox.md)|Austauschdaten zwischen einer Membervariablen und einem Kontrollkästchen auf einer HTML\-Seite.|  
|[CDHtmlDialog::DDX\_DHtml\_ElementText](../Topic/CDHtmlDialog::DDX_DHtml_ElementText.md)|Austauschdaten zwischen einer Membervariablen und einer HTML\-Element\-Eigenschaft auf einer HTML\-Seite.|  
|[CDHtmlDialog::DDX\_DHtml\_Radio](../Topic/CDHtmlDialog::DDX_DHtml_Radio.md)|Austauschdaten zwischen einer Membervariablen und einem Optionsfeld auf einer HTML\-Seite.|  
|[CDHtmlDialog::DDX\_DHtml\_SelectIndex](../Topic/CDHtmlDialog::DDX_DHtml_SelectIndex.md)|Ruft ab oder legt den Index eines Listenfelds auf einer HTML\-Seite fest.|  
|[CDHtmlDialog::DDX\_DHtml\_SelectString](../Topic/CDHtmlDialog::DDX_DHtml_SelectString.md)|Ruft ab oder legt den Anzeigetext eines Listenfeldeintrags \(basierend auf den aktuellen Index\) auf einer HTML\-Seite fest.|  
|[CDHtmlDialog::DDX\_DHtml\_SelectValue](../Topic/CDHtmlDialog::DDX_DHtml_SelectValue.md)|Ruft ab oder legt den Wert eines Listenfeldeintrags \(basierend auf den aktuellen Index\) auf einer HTML\-Seite fest.|  
|[CDHtmlDialog::DestroyModeless](../Topic/CDHtmlDialog::DestroyModeless.md)|Zerstört ein nicht modales Dialogfeld.|  
|[CDHtmlDialog::EnableModeless](../Topic/CDHtmlDialog::EnableModeless.md)|Ermöglicht nicht modale Dialogfelder.|  
|[CDHtmlDialog::FilterDataObject](../Topic/CDHtmlDialog::FilterDataObject.md)|Ermöglicht das Dialogfeld an Filterzwischenablagedatenobjekten, die vom gehosteten Browser erstellt werden.|  
|[CDHtmlDialog::GetControlDispatch](../Topic/CDHtmlDialog::GetControlDispatch.md)|Ruft die `IDispatch`\-Schnittstelle in einem ActiveX\-Steuerelement ab, das im HTML\-Dokument eingebettet ist.|  
|[CDHtmlDialog::GetControlProperty](../Topic/CDHtmlDialog::GetControlProperty.md)|Ruft die angeforderte Eigenschaft des angegebenen ActiveX\-Steuerelements ab.|  
|[CDHtmlDialog::GetCurrentUrl](../Topic/CDHtmlDialog::GetCurrentUrl.md)|Ruft die URL \(Uniform Resource Locator\) zugeordnet mit dem aktuellen Dokument ab.|  
|[CDHtmlDialog::GetDHtmlDocument](../Topic/CDHtmlDialog::GetDHtmlDocument.md)|Ruft die Schnittstelle IHTMLDocument2 auf dem derzeit geladenen HTML\-Dokument ab.|  
|[CDHtmlDialog::GetDropTarget](../Topic/CDHtmlDialog::GetDropTarget.md)|Aufgerufen durch das enthaltende ActiveX\-Steuerelement browsersteuerelement, wenn es als Ablageziel verwendet wird, um das Dialogfeld zu ermöglichen, alternative [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) anzugeben.|  
|[CDHtmlDialog::GetElement](../Topic/CDHtmlDialog::GetElement.md)|Ruft eine Schnittstelle in einem HTML \-\- Element ab.|  
|[CDHtmlDialog::GetElementHtml](../Topic/CDHtmlDialog::GetElementHtml.md)|Ruft die **innerHTML**\-Eigenschaft eines HTML\-Elements ab.|  
|[CDHtmlDialog::GetElementInterface](../Topic/CDHtmlDialog::GetElementInterface.md)|Ruft den angeforderten Schnittstellenzeiger von einem HTML\-Element ab.|  
|[CDHtmlDialog::GetElementProperty](../Topic/CDHtmlDialog::GetElementProperty.md)|Ruft den Wert der Eigenschaft eines HTML\-Elements ab.|  
|[CDHtmlDialog::GetElementText](../Topic/CDHtmlDialog::GetElementText.md)|Ruft die **innerText**\-Eigenschaft eines HTML\-Elements ab.|  
|[CDHtmlDialog::GetEvent](../Topic/CDHtmlDialog::GetEvent.md)|Ruft den **IHTMLEventObj** Zeiger auf das Tagesereignisseobjekt.|  
|[CDHtmlDialog::GetExternal](../Topic/CDHtmlDialog::GetExternal.md)|Ruft die `IDispatch`\-Schnittstelle des Hosts ab.|  
|[CDHtmlDialog::GetHostInfo](../Topic/CDHtmlDialog::GetHostInfo.md)|Ruft die das Benutzeroberfläche\-Funktionen des Hosts ab.|  
|[CDHtmlDialog::GetOptionKeyPath](../Topic/CDHtmlDialog::GetOptionKeyPath.md)|Ruft den Registrierungsschlüssel ab, unter dem Benutzereinstellungen gespeichert werden.|  
|[CDHtmlDialog::HideUI](../Topic/CDHtmlDialog::HideUI.md)|Blendet die Benutzeroberfläche des Hosts aus.|  
|[CDHtmlDialog::IsExternalDispatchSafe](../Topic/CDHtmlDialog::IsExternalDispatchSafe.md)|Gibt an, ob die `IDispatch`\-Schnittstelle des Hosts für die Skripterstellung sicher ist.|  
|[CDHtmlDialog::LoadFromResource](../Topic/CDHtmlDialog::LoadFromResource.md)|Lädt die angegebene Ressource in das ActiveX\-Steuerelement browsersteuerelement.|  
|[CDHtmlDialog::Navigate](../Topic/CDHtmlDialog::Navigate.md)|Navigiert zur angegebenen URL.|  
|[CDHtmlDialog::OnBeforeNavigate](../Topic/CDHtmlDialog::OnBeforeNavigate.md)|Aufgerufen vom Framework vor einem Navigationsereignis ausgelöst wird.|  
|[CDHtmlDialog::OnDocumentComplete](../Topic/CDHtmlDialog::OnDocumentComplete.md)|Aufgerufen vom Framework, um eine Anwendung zu benachrichtigen, wenn ein Dokument den `READYSTATE_COMPLETE` Zustand erreicht hat.|  
|[CDHtmlDialog::OnDocWindowActivate](../Topic/CDHtmlDialog::OnDocWindowActivate.md)|Aufgerufen vom Framework, wenn das Dokumentfenster aktiviert oder deaktiviert ist.|  
|[CDHtmlDialog::OnFrameWindowActivate](../Topic/CDHtmlDialog::OnFrameWindowActivate.md)|Aufgerufen vom Framework, wenn das Rahmenfenster aktiviert oder deaktiviert ist.|  
|[CDHtmlDialog::OnInitDialog](../Topic/CDHtmlDialog::OnInitDialog.md)|Als Reaktion auf **WM\_INITDIALOG** die Meldung aufgerufen.|  
|[CDHtmlDialog::OnNavigateComplete](../Topic/CDHtmlDialog::OnNavigateComplete.md)|Aufgerufen durch das Framework nach einem Navigationsereignis wurde abgeschlossen.|  
|[CDHtmlDialog::ResizeBorder](../Topic/CDHtmlDialog::ResizeBorder.md)|Alarmiert das Objekt, dass sein Rahmenleerzeichen Größe ändern muss.|  
|[CDHtmlDialog::SetControlProperty](../Topic/CDHtmlDialog::SetControlProperty.md)|Legt die Eigenschaft eines ActiveX\-Steuerelements auf einen neuen Wert fest.|  
|[CDHtmlDialog::SetElementHtml](../Topic/CDHtmlDialog::SetElementHtml.md)|Legt die Eigenschaft eines HTML\-Elements **innerHTML** fest.|  
|[CDHtmlDialog::SetElementProperty](../Topic/CDHtmlDialog::SetElementProperty.md)|Legt eine Eigenschaft eines HTML\-Elements fest.|  
|[CDHtmlDialog::SetElementText](../Topic/CDHtmlDialog::SetElementText.md)|Legt die Eigenschaft eines HTML\-Elements **innerText**  fest.|  
|[CDHtmlDialog::SetExternalDispatch](../Topic/CDHtmlDialog::SetExternalDispatch.md)|Legt die `IDispatch`\-Schnittstelle des Hosts fest.|  
|[CDHtmlDialog::SetHostFlags](../Topic/CDHtmlDialog::SetHostFlags.md)|Legt die das Benutzeroberfläche\-Flags des Hosts fest.|  
|[CDHtmlDialog::ShowContextMenu](../Topic/CDHtmlDialog::ShowContextMenu.md)|Aufgerufen, wenn ein Kontextmenü im Begriff ist angezeigt werden.|  
|[CDHtmlDialog::ShowUI](../Topic/CDHtmlDialog::ShowUI.md)|Zeigt die Benutzeroberfläche des Hosts an.|  
|[CDHtmlDialog::TranslateAccelerator](../Topic/CDHtmlDialog::TranslateAccelerator.md)|Aufgerufen, um Menüzugriffstastenmeldungen zu verarbeiten.|  
|[CDHtmlDialog::TranslateUrl](../Topic/CDHtmlDialog::TranslateUrl.md)|Aufgerufen, um das geladen werden URL zu ändern.|  
|[CDHtmlDialog::UpdateUI](../Topic/CDHtmlDialog::UpdateUI.md)|Aufgerufen, um den Host zu benachrichtigen, dass der Befehlszustand geändert hat.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDHtmlDialog::m\_bUseHtmlTitle](../Topic/CDHtmlDialog::m_bUseHtmlTitle.md)|Gibt an, ob dem Namen des HTML\-Dokuments als die Dialogfeldbeschriftung verwendet.|  
|[CDHtmlDialog::m\_nHtmlResID](../Topic/CDHtmlDialog::m_nHtmlResID.md)|Ressourcen\-ID der angezeigt werden HTML\-Ressource.|  
|[CDHtmlDialog::m\_pBrowserApp](../Topic/CDHtmlDialog::m_pBrowserApp.md)|Ein Zeiger auf eine bereitzustellende Webbrowseranwendung.|  
|[CDHtmlDialog::m\_spHtmlDoc](../Topic/CDHtmlDialog::m_spHtmlDoc.md)|Ein Zeiger auf ein HTML\-Dokument.|  
|[CDHtmlDialog::m\_strCurrentUrl](../Topic/CDHtmlDialog::m_strCurrentUrl.md)|Der aktuelle URL.|  
|[CDHtmlDialog::m\_szHtmlResID](../Topic/CDHtmlDialog::m_szHtmlResID.md)|Zeichenfolgenversion der HTML\-Ressourcen\-ID|  
  
## Hinweise  
 **CDHtmlDialog**  kann das von einer HTML\-Ressource oder einer URL angezeigt werden, HTML laden, entweder.  
  
 `CDHtmlDialog` kann Datenaustausch mit HTML\-Steuerelemente ausführen und Behandeln von HTML\-Steuerelementen, wie Schaltfläche klickt.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 `CDHtmlDialog`  
  
## Anforderungen  
 **Header:** afxdhtml.h  
  
## Siehe auch  
 [MFC\-Beispiel DHtmlExplore](../../top/visual-cpp-samples.md)   
 [DDX\_DHtml Helper Macros](../../mfc/reference/ddx-dhtml-helper-macros.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)