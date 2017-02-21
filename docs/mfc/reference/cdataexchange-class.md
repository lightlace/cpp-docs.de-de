---
title: "CDataExchange Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDataExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataExchange class"
  - "DDV (dialog data validation)"
  - "DDV (dialog data validation), custom DDV routines"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch)"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch), between dialog and CDialog"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch), custom DDX routines"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch), direction of exchange"
  - "DDX/DDV"
  - "DDX/DDV, CDataExchange class"
  - "DDX/DDV, Technical Note 26"
  - "exchanging data between dialogs and CDialogs"
  - "m_bSaveAndValidate"
  - "Validieren von Daten, dialog box data entry"
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CDataExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützt den Dialogdatenaustausch \(DDX\) und die Routinen der Dialogfelddatenvalidierung \(DDV\), die von der Microsoft Foundation verwendet werden, klassifiziert.  
  
## Syntax  
  
```  
class CDataExchange  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDataExchange::CDataExchange](../Topic/CDataExchange::CDataExchange.md)|Erstellt ein `CDataExchange`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDataExchange::Fail](../Topic/CDataExchange::Fail.md)|Aufgerufen, wenn die Validierung fehlschlägt.  Wenn des Fokus auf das vorherige Steuerelement und zu den löst eine Ausnahme.|  
|[CDataExchange::PrepareCtrl](../Topic/CDataExchange::PrepareCtrl.md)|Bereitet das angegebene Steuerelement für Datenaustausch oder Validierung vor.  Verwenden Sie für nonedit Steuerelemente.|  
|[CDataExchange::PrepareEditCtrl](../Topic/CDataExchange::PrepareEditCtrl.md)|Bereitet das angegebene Bearbeitungssteuerelement für Datenaustausch oder Validierung vor.|  
|[CDataExchange::PrepareOleCtrl](../Topic/CDataExchange::PrepareOleCtrl.md)|Bereitet das angegebene OLE\-Steuerelement für Datenaustausch oder Validierung vor.  Verwenden Sie für nonedit Steuerelemente.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDataExchange::m\_bSaveAndValidate](../Topic/CDataExchange::m_bSaveAndValidate.md)|Flag für die Richtung von DDX und von DDV.|  
|[CDataExchange::m\_pDlgWnd](../Topic/CDataExchange::m_pDlgWnd.md)|Das Dialogfeld oder das Fenster, in dem der Datenaustausch stattfindet.|  
  
## Hinweise  
 `CDataExchange` hat keine Basisklasse.  
  
 Verwenden Sie diese Klasse, wenn Sie Datenaustauschroutinen für benutzerdefinierte Datentypen oder Steuerelemente schreiben oder wenn Sie eigene Datenvalidierungsroutinen schreiben.  Weitere Informationen über das Schreiben eigener DDX\- und DDV\-Routinen, finden Sie unter [Technischer Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md).  Eine Übersicht über DDX und von DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfelder](../../mfc/dialog-boxes.md).  
  
 Ein Objekt stellt die `CDataExchange` Kontextinformationen zur Verfügung, die damit DDX und DDV erforderlich sind, stattfindet.  Das Flag `m_bSaveAndValidate` ist **FALSE**, wenn DDX verwendet wird, um die Anfangswerte von Dialogfeld\-Steuerelemente von den Datenmember auszufüllen.  Das Flag `m_bSaveAndValidate` ist **TRUE**, wenn DDX verwendet wird, um die aktuellen Werte von Dialogfeld\-Steuerelemente in Datenmember festzulegen und wenn DDV verwendet wird, um die Datenwerte zu überprüfen.  Wenn die DDV\-Validierung fehl, wird die DDV\-Prozedur ein Meldungsfeld an, das den Eingabefehler erläutert.  Die DDV\-Prozedur **Fail** ruft dann auf, um den Fokus auf das Steuerelement problembehaftete zurückzusetzen und eine Ausnahme auszulösen, um dem Validierungsprozess zu beenden.  
  
## Vererbungshierarchie  
 `CDataExchange`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC\-Beispiel VIEWEX](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)   
 [CWnd::UpdateData](../Topic/CWnd::UpdateData.md)