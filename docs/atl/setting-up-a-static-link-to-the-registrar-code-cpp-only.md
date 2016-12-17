---
title: "Setting Up a Static Link to the Registrar Code (C++ Only)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verknüpfen [C++], to ATL Registrar code"
  - "statically linking to ATL Registrar code"
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Setting Up a Static Link to the Registrar Code (C++ Only)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+\-Clients können eine statische Verbindung zum Code der Registrierungsstelle erstellen.  Statische Verknüpfungen Analyse\- der Registrierungsstelle fügt ungefähr 5K einem Releasebuild hinzu.  
  
 Die einfachste Möglichkeit, die statische Verknüpfung zu installieren wird davon ausgegangen, dass Sie [DECLARE\_REGISTRY\_RESOURCEID](../Topic/DECLARE_REGISTRY_RESOURCEID.md) in der Deklaration des Objekts angegeben haben.  \(Dies ist die standardmäßige Spezifikation, die vom ATL verwendet wird.\)  
  
### So fügen Sie eine statische Verbindung mit DECLARE\_REGISTRY\_RESOURCEID erstellen  
  
1.  Geben Sie [\/D](../build/reference/d-preprocessor-definitions.md)`_ATL_STATIC_REGISTRY` anstelle von \/D **\_ATL\_DLL** an.  
  
2.  Kompilieren Sie erneut.  
  
## Siehe auch  
 [Registrierungskomponente \(Registrar\)](../atl/atl-registry-component-registrar.md)