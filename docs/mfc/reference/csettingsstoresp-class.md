---
title: "CSettingsStoreSP Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSettingsStoreSP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSettingsStoreSP class"
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CSettingsStoreSP Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CSettingsStoreSP`\-Klasse ist eine Hilfsprogrammklasse, die Sie verwenden können, um Instanzen [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md) zu erstellen.  
  
## Syntax  
  
```  
class CSettingsStoreSP  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](../Topic/CSettingsStoreSP::CSettingsStoreSP.md)|Erstellt ein `CSettingsStoreSP`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSettingsStoreSP::Create](../Topic/CSettingsStoreSP::Create.md)|Erstellt eine Instanz einer Klasse, die von `CSettingsStore` abgeleitet wird.|  
|[CSettingsStoreSP::SetRuntimeClass](../Topic/CSettingsStoreSP::SetRuntimeClass.md)|Legt die Laufzeitklasse fest.  Die `Create`\-Methode verwendet die Laufzeitklasse, um zu bestimmen, welche Klasse zum Erstellen von Objekten.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|`m_dwUserData`|Benutzerdefinierte Benutzerdaten, die im `CSettingsStoreSP`\-Objekt gespeichert wird.  Sie stellen diese Daten im Konstruktor des Objekts `CSettingsStoreSP`.|  
|`m_pRegistry`|`CSettingsStore` von abgeleitetes Objekt, das die `Create`\-Methode erstellt.|  
  
## Hinweise  
 Sie können die `CSettingsStoreSP`\-Klasse verwenden, um alle MFC\-Registrierungsvorgänge zu anderen Speicherorten, wie einer XML\-Datei oder einer Datenbank umleiten.  Führen Sie dazu folgende Schritte aus:  
  
1.  Erstellen Sie eine Klasse \(z `CMyStore`\) und leiten Sie diese von `CSettingsStore`.  
  
2.  Verwenden Sie [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) und [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md)\-Makros mit der benutzerdefinierten `CSettingsStore`\-Klasse, um dynamische Erstellung zu aktivieren.  
  
3.  Überschreiben Sie die virtuellen Funktionen und implementieren Sie die `Read` und `Write`\-Funktionen in der benutzerdefinierten Klasse.  Implementieren Sie jede andere Funktionen, um Daten zu dem gewünschten Speicherort zu lesen und zu schreiben.  
  
4.  In der Anwendung rufen Sie `CSettingsStoreSP::SetRuntimeClass` auf und übergeben Sie in einen Zeiger auf [CRuntimeClass Structure](../../mfc/reference/cruntimeclass-structure.md) sie von der Klasse.  
  
 Wenn das Framework in der Regel auf die Registrierung zugreifen kann, instanziiert es jetzt dynamisch die benutzerdefinierte Klasse und verwendet sie, um Daten zu lesen oder zu schreiben.  
  
 `CSettingsStoreSP::SetRuntimeClass` verwendet eine globale statische Variable.  Daher ist nur ein benutzerdefinierter Speicher auf einmal verfügbar.  
  
## Anforderungen  
 **Header:** afxsettingsstore.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md)