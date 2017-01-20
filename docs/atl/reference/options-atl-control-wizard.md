---
title: "Optionen, ATL-Steuerelement-Assistent"
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
  - "vc.codewiz.class.atl.control.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Steuerelement-Assistent, Optionen"
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
caps.latest.revision: 14
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Optionen, ATL-Steuerelement-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügen Sie die Zusammenfassung der Suchergebnisse hier ein.  
  
 Sie verwenden diese Seite des Assistenten, um den Typ des zu erstellenden Steuerelements und den Umfang der integrierten Schnittstellenunterstützung festzulegen.  
  
## UIElement-Liste  
 **Steuerelementtyp**  
 Der Typ des zu erstellenden Steuerelements.  
  
-   **Standardsteuerelement: ein ActiveX\-Steuerelement.**  
  
-   **Zusammengesetztes Steuerelement**: Ein ActiveX\-Steuerelement, das \(ähnlich wie ein Dialogfeld\) andere ActiveX\- oder Windows\-Steuerelemente enthalten kann.  Ein zusammengesetztes Steuerelement umfasst folgende Komponenten:  
  
    -   Eine Vorlage für das Dialogfeld, durch das das zusammengesetzte Steuerelement implementiert wird.  
  
    -   Die benutzerdefinierte Ressource REGISTRY, durch die das zusammengesetzte Steuerelement beim ersten Aufrufen automatisch registriert wird.  
  
    -   Eine C\+\+\-Klasse, durch die das zusammengesetzte Steuerelement implementiert wird.  
  
    -   Eine COM\-Schnittstelle, die durch das zusammengesetzte Steuerelement verfügbar gemacht wird.  
  
    -   Eine HTML\-Testseite mit dem zusammengesetzten Steuerelement.  
  
     Um darauf hinzuweisen, dass das Steuerelement als Fenster dargestellt ist, wird [CComControlBase::m\_bWindowOnly](../Topic/CComControlBase::m_bWindowOnly.md) durch dieses Steuerelement standardmäßig auf true festgelegt.  Zusätzlich wird eine Ereignissenkenzuordnung implementiert.  Weitere Informationen finden Sie unter [Unterstützung für DHTML\-Steuerelemente](../../atl/atl-support-for-dhtml-controls.md).  
  
-   **DHTML\-Steuerelement**: Ein ATL DHTML\-Steuerelement definiert die Benutzeroberfläche unter Verwendung von HTML.  Die DHTML\-UI\-Klasse enthält eine COM\-Zuordnung.  Um darauf hinzuweisen, dass das Steuerelement als Fenster dargestellt ist, wird [CComControlBase::m\_bWindowOnly](../Topic/CComControlBase::m_bWindowOnly.md) durch dieses Steuerelement standardmäßig auf true festgelegt.  
  
     Weitere Informationen finden Sie unter [Identifying the Elements of the DHTML Control Project](../../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
 **Minimal\-Steuerelement**  
 Unterstützt ausschließlich die Schnittstellen, die für die meisten Container unverzichtbar sind.  Sie können jeden Steuerelementtyp als **Minimal\-Steuerelement** konfigurieren. Sie können z. B. ein Minimal\-Standardsteuerelement, ein zusammengesetztes Minimal\-Steuerelement oder ein Minimal\-DHTML\-Steuerelement erstellen.  
  
 **Aggregation**  
 Fügt dem erstellten Steuerelement Aggregationsunterstützung hinzu.  Weitere Informationen finden Sie unter [Aggregation](../../atl/aggregation.md).  
  
-   **Ja**: Erstellt ein Steuerelement, das aggregiert werden kann.  
  
-   **Nein**: Erstellt ein Steuerelement, das nicht aggregiert werden kann.  
  
-   **Nur**: Erstellt ein Steuerelement, das nur durch die Aggregation instanziiert werden kann.  
  
 **Threadmodell**  
 Legt das vom Steuerelement verwendete Threadmodell fest.  
  
-   **Einfach**: Das Steuerelement wird nur im primären COM\-Thread ausgeführt.  
  
-   **Apartment**: Das Steuerelement kann in jedem beliebigen Singlethreadapartment erstellt werden.  Der Standardwert.  
  
 **Interface**  
 Der Schnittstellentyp, den dieses Steuerelement gegenüber dem Container verfügbar macht.  
  
-   **Dual**: Erstellt eine Schnittstelle, die Eigenschaften und Methoden durch `IDispatch` und direkt durch die VTBL verfügbar macht.  
  
-   **Benutzerdefiniert**: Erstellt eine Schnittstelle, die Methoden direkt durch eine VTBL verfügbar macht.  
  
     Bei Auswahl von **Benutzerdefiniert** können Sie angeben, dass das Steuerelement **Automatisierungskompatibel** sein soll.  Bei Auswahl von **Automatisierungskompatibel** fügt der Assistent der Schnittstelle in der IDL das [oleautomation](../../windows/oleautomation.md)\-Attribut hinzu. Anschließend kann die Schnittstelle durch den universellen Marshaler in oleaut32.dll gemarshallt werden.  Weitere Informationen finden Sie unter [Marshaling Details](http://msdn.microsoft.com/library/windows/desktop/ms692621) im [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
     Zusätzlich müssen bei Auswahl von **Automatisierungskompatibel** alle Parameter für alle Methoden im Steuerelement **VARIANT**\-kompatibel sein.  
  
 **Unterstützung**  
 Fügt dem Steuerelement weitere unterschiedliche Unterstützungsfunktionen hinzu.  
  
-   **Verbindungspunkte**: Aktiviert Verbindungspunkte für das Objekt, indem die Klasse des Objekts von [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) abgeleitet und das Verfügbarmachen einer Quellschnittstelle ermöglicht wird.  
  
-   **Lizenziert**: Fügt dem Steuerelement Unterstützung für die [Lizenzierung](http://msdn.microsoft.com/library/windows/desktop/ms690543) hinzu.  Das Aufnehmen lizenzierter Steuerelemente ist nur möglich, wenn der Clientcomputer über die richtige Lizenz verfügt.  
  
## Siehe auch  
 [ATL\-Steuerelement\-Assistent](../../atl/reference/atl-control-wizard.md)