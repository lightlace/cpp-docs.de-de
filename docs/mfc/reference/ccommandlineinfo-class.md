---
title: "CCommandLineInfo Class"
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
  - "CCommandLineInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application flags [C++]"
  - "argv argument"
  - "CCommandLineInfo class"
  - "Befehlszeile, Analysieren"
  - "Analysieren, Befehlszeilenargumente"
  - "Startcode, parsing command-line arguments"
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
caps.latest.revision: 21
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CCommandLineInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unterstützt, wenn die Befehlszeile beim Anwendungsstart analysiert wird.  
  
## Syntax  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CCommandLineInfo::CCommandLineInfo](../Topic/CCommandLineInfo::CCommandLineInfo.md)|Erstellt ein Objekt `CCommandLineInfo`.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CCommandLineInfo::ParseParam](../Topic/CCommandLineInfo::ParseParam.md)|Überschreiben Sie diesen Rückruf, um einzelne Parameter zu analysieren.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CCommandLineInfo::m\_bRunAutomated](../Topic/CCommandLineInfo::m_bRunAutomated.md)|Gibt an, dass die **\/Automation**\-Befehlszeilenoption gefunden wurde.|  
|[CCommandLineInfo::m\_bRunEmbedded](../Topic/CCommandLineInfo::m_bRunEmbedded.md)|Gibt an, dass die **\/Embedding**\-Befehlszeilenoption gefunden wurde.|  
|[CCommandLineInfo::m\_bShowSplash](../Topic/CCommandLineInfo::m_bShowSplash.md)|Gibt an, ob ein Begrüßungsbildschirm angezeigt wird.|  
|[CCommandLineInfo::m\_nShellCommand](../Topic/CCommandLineInfo::m_nShellCommand.md)|Gibt den Shellbefehl für verarbeitet werden.|  
|[CCommandLineInfo::m\_strDriverName](../Topic/CCommandLineInfo::m_strDriverName.md)|Gibt den Namen des Treibers an, wenn der Shellbefehl Druckt in ist; andernfalls leer.|  
|[CCommandLineInfo::m\_strFileName](../Topic/CCommandLineInfo::m_strFileName.md)|Gibt den zu öffnenden an oder gedruckt wurde Dateinamen; leer, wenn der Shellbefehl neu oder DDE ist.|  
|[CCommandLineInfo::m\_strPortName](../Topic/CCommandLineInfo::m_strPortName.md)|Gibt den Anschlussnamen an, wenn der Shellbefehl Druckt in ist; andernfalls leer.|  
|[CCommandLineInfo::m\_strPrinterName](../Topic/CCommandLineInfo::m_strPrinterName.md)|Gibt den Druckernamen an, wenn der Shellbefehl Druckt in ist; andernfalls leer.|  
|[CCommandLineInfo::m\_strRestartIdentifier](../Topic/CCommandLineInfo::m_strRestartIdentifier.md)|Gibt den eindeutigen Neustartbezeichner für den Neustart\-Manager an, wenn diese vom Neustart\-Manager erneut ausgelöst hat.|  
  
## Hinweise  
 Eine MFC\-Anwendung erstellt in der Regel eine lokale Instanz dieser Klasse in der [InitInstance](../Topic/CWinApp::InitInstance.md)\-Funktion des Anwendungsobjekts.  Dieses Objekt wird dann an [CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md) übergeben, das [ParseParam](../Topic/CCommandLineInfo::ParseParam.md) wiederholt aufgerufen wird, um das `CCommandLineInfo`\-Objekt auszufüllen.  Das `CCommandLineInfo`\-Objekt wird dann an [CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md) übergeben, um Befehlszeilenargumente und \-Flags zu behandeln.  
  
 Sie können dieses Objekt verwenden, um die folgenden Befehlszeilenoptionen und die Parameter zu kapseln:  
  
|Befehlszeilenargument|Ausgeführter Befehl|  
|---------------------------|-------------------------|  
|*App*|Neue Datei.|  
|*app* Dateiname|Datei öffnen.|  
|*app* **\/p** Dateiname|Datei auf dem Standarddrucker drucken.|  
|*app* **\/pt** Dateiname Druckertreiberanschluss|Datei auf dem angegebenen Drucker drucken.|  
|*app* **\/dde**|Starten Sie oben und erwarten Sie DDE\-Befehl.|  
|*app* **\/Automation**|Starten Sie oben als OLE\-Automatisierungs\-Server.|  
|*app* **\/Embedding**|Anfangsbis Bearbeitung ein eingebettetes OLE\-Element.|  
|*app* **\/Register**<br /><br /> *app* **\/Regserver**|Informiert die Anwendung, alle Registrierungsaufgaben auszuführen.|  
|*app* **\/Unregister**<br /><br /> *app* **\/Unregserver**|Das informiert die Anwendung, alle UNRegistrierung Aufgaben auszuführen.|  
  
 Ableiten einer neuen Klasse von `CCommandLineInfo`, um andere Flags und Parameterwerte zu behandeln.  Überschreiben [ParseParam](../Topic/CCommandLineInfo::ParseParam.md), um der neuen Flags zu behandeln.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)   
 [CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md)