---
title: "CSnapInPropertyPageImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSnapInPropertyPageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSnapInPropertyPageImpl class"
  - "Eigenschaftenseiten, ATL"
  - "snap-ins"
  - "snap-ins, Eigenschaftenseiten"
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSnapInPropertyPageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Implementieren eines Snap\-Ineigenschaftenseitenobjekts bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
CSnapInPropertyPageImpl : public CDialogImplBase  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](../Topic/CSnapInPropertyPageImpl::CSnapInPropertyPageImpl.md)|Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CancelToClose](../Topic/CSnapInPropertyPageImpl::CancelToClose.md)|Ändert den Status der **OK** und **Abbrechen** Schaltflächen.|  
|[CSnapInPropertyPageImpl::Create](../Topic/CSnapInPropertyPageImpl::Create.md)|Initialisiert `CSnapInPropertyPageImpl` ein neu erstelltes Objekt.|  
|[CSnapInPropertyPageImpl::OnApply](../Topic/CSnapInPropertyPageImpl::OnApply.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Schaltfläche **Jetzt übernehmen** bei Verwendung eines assistentenartigeigenschaftenblatts klickt.|  
|[CSnapInPropertyPageImpl::OnHelp](../Topic/CSnapInPropertyPageImpl::OnHelp.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Schaltfläche **Hilfe** bei Verwendung eines assistentenartigeigenschaftenblatts klickt.|  
|[CSnapInPropertyPageImpl::OnKillActive](../Topic/CSnapInPropertyPageImpl::OnKillActive.md)|Aufgerufen vom Framework, wenn die aktuelle Seite nicht mehr aktiv ist.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](../Topic/CSnapInPropertyPageImpl::OnQueryCancel.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Schaltfläche klickt **Abbrechen** und bevor das Löschen stattgefunden hat.|  
|[CSnapInPropertyPageImpl::OnReset](../Topic/CSnapInPropertyPageImpl::OnReset.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Schaltfläche **Zurücksetzen** bei Verwendung eines assistentenartigeigenschaftenblatts klickt.|  
|[CSnapInPropertyPageImpl::OnSetActive](../Topic/CSnapInPropertyPageImpl::OnSetActive.md)|Aufgerufen vom Framework, wenn die aktuelle Seite aktiv ist.|  
|[CSnapInPropertyPageImpl::OnWizardBack](../Topic/CSnapInPropertyPageImpl::OnWizardBack.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Schaltfläche **Zurück** bei Verwendung eines assistentenartigeigenschaftenblatts klickt.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](../Topic/CSnapInPropertyPageImpl::OnWizardFinish.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Schaltfläche **Fertig stellen** bei Verwendung eines assistentenartigeigenschaftenblatts klickt.|  
|[CSnapInPropertyPageImpl::OnWizardNext](../Topic/CSnapInPropertyPageImpl::OnWizardNext.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Schaltfläche `Next` bei Verwendung eines assistentenartigeigenschaftenblatts klickt.|  
|[CSnapInPropertyPageImpl::QuerySiblings](../Topic/CSnapInPropertyPageImpl::QuerySiblings.md)|Leitet die aktuelle Meldung an alle Seiten des Eigenschaftenblatts weiter.|  
|[CSnapInPropertyPageImpl::SetModified](../Topic/CSnapInPropertyPageImpl::SetModified.md)|aufrufen, um die Schaltfläche **Jetzt übernehmen** zu aktivieren oder zu deaktivieren.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m\_psp](../Topic/CSnapInPropertyPageImpl::m_psp.md)|Die Struktur Windows **PROPSHEETPAGE** wird vom `CSnapInPropertyPageImpl`\-Objekt.|  
  
## Hinweise  
 `CSnapInPropertyPageImpl` stellt eine grundlegende Implementierung für ein Snap\-Ineigenschaftenseitenobjekt bereit.  Die grundlegenden Features einer Snap\-Ineigenschaftenseite werden mit einer Reihe verschiedener Schnittstellen implementiert und Typen zuordnen.  
  
## Vererbungshierarchie  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## Anforderungen  
 **Header:**  atlsnap.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)