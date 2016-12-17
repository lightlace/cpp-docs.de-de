---
title: "CSettingsStore Class"
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
  - "CSettingsStore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSettingsStore class"
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
caps.latest.revision: 29
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# CSettingsStore Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Umschließt die Windows\-API\-Funktionen ein und stellt eine objektorientierte Schnittstelle bereit, auf der Sie verwenden, um die Registrierung zuzugreifen.  
  
## Syntax  
  
```  
class CSettingsStore : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSettingsStore::CSettingsStore](../Topic/CSettingsStore::CSettingsStore.md)|Erstellt ein `CSettingsStore`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSettingsStore::Close](../Topic/CSettingsStore::Close.md)|Schließt den geöffneten Registrierungsschlüssel.|  
|[CSettingsStore::CreateKey](../Topic/CSettingsStore::CreateKey.md)|Öffnet den angegebenen Schlüssel oder erstellt es, wenn er nicht vorhanden ist.|  
|[CSettingsStore::DeleteKey](../Topic/CSettingsStore::DeleteKey.md)|Löscht den angegebenen Schlüssel und alle untergeordneten Elemente.|  
|[CSettingsStore::DeleteValue](../Topic/CSettingsStore::DeleteValue.md)|Löscht den angegebenen Wert der geöffneten Schlüssel.|  
|[CSettingsStore::Open](../Topic/CSettingsStore::Open.md)|Öffnet den angegebenen Schlüssel.|  
|[CSettingsStore::Read](../Topic/CSettingsStore::Read.md)|Ruft die Daten für einen angegebenen Schlüsselwert ab.|  
|[CSettingsStore::Write](../Topic/CSettingsStore::Write.md)|Schreibt einen Wert zur Registrierung unter die geöffnete Schlüssel.|  
  
## Hinweise  
 Die Memberfunktionen `CreateKey` und `Open` sind sehr ähnlich.  Wenn der Registrierungsschlüssel bereits vorhanden ist, `CreateKey` und `Open`\-Funktion auf dieselbe Weise.  Wenn der Registrierungsschlüssel nicht vorhanden ist, erstellt `CreateKey` ihn, während `Open` einen Fehlerwert zurückgibt.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie das geöffnete verwendet und Lesemethoden `CSettingsStore` darstellen.  Dieser Codeausschnitt ist Teil [QuickInfo\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_ToolTipDemo#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_ToolTipDemo#1)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSettingsStore](../../mfc/reference/csettingsstore-class.md)  
  
## Anforderungen  
 **Header:** afxsettingsstore.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)