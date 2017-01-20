---
title: "CMultiPageDHtmlDialog Class"
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
  - "CMultiPageDHtmlDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiPageDHtmlDialog class"
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiPageDHtmlDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein mehrseitigen Dialogfeld werden mehrere HTML\-Seiten sequenziell an und behandelt die Ereignisse von jeder Seite.  
  
## Syntax  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](../Topic/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog.md)|Erstellt ein mehrseitiges \(AssistentFormat\) DHTML\-Dialogfeldobjekt.|  
|[CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog](../Topic/CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog.md)|Zerstört ein mehrseitiges DHTML\-Dialogfeldobjekt.|  
  
## Hinweise  
 Der Mechanismus für das diese Vorgehensweise ist [DHTML und URL\-Ereigniszuordnung](assetId:///2a7332f0-79d7-46e4-b816-0a618c46777a), das [eingebettete Ereigniszuordnungen](../Topic/BEGIN_EMBED_DHTML_EVENT_MAP.md) für jede Seite enthält.  
  
## Beispiel  
 Dieses Dialogfeld mehrseitige akzeptiert drei HTML\-Ressourcen an, die einfache assistentenbasierte Funktionen definieren.  Die erste Seite verfügt über eine `Next` Schaltfläche, die eine zweite **Zurück** und `Next` Schaltfläche und das dritte **Zurück** eine Schaltfläche.  Wenn einer der Schaltflächen gedrückt wird, ruft [CDHtmlDialog::LoadFromResource](../Topic/CDHtmlDialog::LoadFromResource.md) einer Handlerfunktion, um die entsprechenden neuen Seite zu laden.  
  
 Die entsprechenden Teile der Klassendeklaration \(in CMyMultiPageDlg.h\):  
  
 [!CODE [NVC_MFCDocView#181](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#181)]  
  
 Die entsprechenden Teile der Klassenimplementierung \(in CMyMultipageDlg.cpp\):  
  
 [!CODE [NVC_MFCDocView#182](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#182)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## Anforderungen  
 **Header:** afxdhtml.h  
  
## Siehe auch  
 [CDHtmlDialog Class](../../mfc/reference/cdhtmldialog-class.md)   
 [Multipage DHTML and URL Event Maps \(NIB\)](assetId:///2a7332f0-79d7-46e4-b816-0a618c46777a)