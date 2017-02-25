---
title: "Verwenden des OLE/COM-Objektkatalogs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], Anzeigen von internen Schnittstellen"
  - "Objektkatalog für Automatisierungsobjekte"
  - "OLE/COM-Objektkatalog"
ms.assetid: a3359e31-2869-451d-9571-129b4e8b41f0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Verwenden des OLE/COM-Objektkatalogs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie können den OLE\/COM\-Objektkatalog verwenden, um den Schnittstellen eines Steuerelements anzuzeigen.  
  
### So verwenden Sie den OLE\/COM\-Objektkatalog  
  
1.  Starten Sie den OLE\/COM\-Objektkatalog \(oleview.exe\), der sich im Ordner \\Programme \(x86\)\\Windows Kits\\8.0\\bin\\x86\\ befindet.  
  
2.  In der Kategorie **Objektklassen, gruppiert nach Komponente** im Viewer, öffnen Sie den Ordner **Automatisierungsobjekte**, die registrierten Automatisierungsobjekte anzuzeigen.  
  
3.  Wählen Sie eines der Steuerelemente aus.  Einige Registerkarten werden im rechten Bereich; die Schnittstellen, die das Steuerelement implementiert werden, werden auf der Registerkarte **Registrierung** angezeigt.  
  
    -   Wenn Sie das Kontextmenü für ein Steuerelement im linken Bereich **Typinformationen anzeigen** öffnen und dann auswählen, wird im ITypeInfo\-Viewer eine rekonstruierte IDL\- oder ODL\-Datei angezeigt.  
  
    -   Wenn Sie den Steuerelementknoten im linken Bereich erweitern, wird eine Liste der Schnittstellen im Objekt angezeigt.  Wenn eine Schnittstelle auswählen, wird der Registrierungseintrag im rechten Bereich angezeigt.  
  
    -   Wenn Sie das Kontextmenü für eine Schnittstelle **Ansicht** öffnen und dann auswählen, wird vom OLE\/COM\-Objektkatalog ein Dialogfeld an, das die GUID darstellt, sodass die Schnittstelle und eine Option zum Anzeigen, falls verfügbar.  Das **Typinformationen anzeigen** auswählen wird ein Teil einer rekonstruierten IDL\-Datei angezeigt, die der Oberfläche im ITypeInfo\-Viewer spezifisch ist.  
  
    -   im ITypeInfo\-Viewer können Sie einen Schnittstellenmember in der Strukturansicht auswählen, um die Accessormethodensignaturen im rechten Bereich anzuzeigen.  
  
## Siehe auch  
 [Verwenden von ActiveX\-Steuerelementen](../../data/ado-rdo/using-activex-controls.md)