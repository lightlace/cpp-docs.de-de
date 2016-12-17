---
title: "Using Replaceable Parameters (The Registrar&#39;s Preprocessor)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "AddReplacement"
  - "ClearReplacements"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%MODULE%"
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Using Replaceable Parameters (The Registrar&#39;s Preprocessor)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ersetzbare Parameter ermöglichen dem Client einer Registrierungsstelle, um Ablaufdaten anzugeben.  Hierzu, wartet die Registrierungsstelle eine Ersatzzuordnung in die es die Werte eingeben, die mit den ersetzbaren Parametern im Skript zugeordnet sind.  Die Registrierungsstelle macht diese Einträge zur Laufzeit.  
  
##  <a name="_atl_using_.25.module.25"></a> Verwenden %MODULE%  
 [ATL\-Steuerelement\-Assistent](../atl/reference/atl-control-wizard.md) automatisch generiert ein Skript, das `%MODULE%` verwendet.  ATL verwendet diesen ersetzbaren Parameter für den tatsächlichen Speicherort der DLL oder der EXE\-Datei Ihres Servers.  
  
## Verketten von Ablaufdaten mit Skript\-Daten  
 Eine andere Verwendung des Präprozessors ist, Ablaufdaten mit Skriptdaten zu verketten.  Angenommen, ein Eintrag erforderlich ist, der einen vollständigen Pfad zu einem Modul mit der Zeichenfolge "`, 1` enthält", das am Ende angefügt wird.  Zuerst definieren Sie die folgenden Erweiterung:  
  
```  
'MySampleKey' = s '%MODULE%, 1'  
```  
  
 Anschließend bevor Sie ein des Skripts aufrufen, das die Methoden verarbeitet, die in [Aufrufen von Skripts](../atl/invoking-scripts.md) aufgeführt sind, fügen Sie eine Ersetzung der Zuordnung:  
  
 [!CODE [NVC_ATL_Utilities#113](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#113)]  
  
 Während der Analyse des Skripts, erweitert die Registrierungsstelle `'%MODULE%, 1'` zu `c:\mycode\mydll.dll, 1`.  
  
> [!NOTE]
>  In einem Registrierungsstellenskript ist 4K die maximale Scheingröße.  \(A\-Token erkennbare ist jedes Element in der Syntax.\) Dies schließt ein Token, die vom Präprozessor erstellt oder erweitert wurden.  
  
> [!NOTE]
>  Um Wiederbeschaffungswerte zur Laufzeit zu ersetzen, entfernen Sie den Aufruf im Skript für den [DECLARE\_REGISTRY\_RESOURCE](../Topic/DECLARE_REGISTRY_RESOURCE.md) oder [DECLARE\_REGISTRY\_RESOURCEID](../Topic/DECLARE_REGISTRY_RESOURCEID.md)\-Makro.  Stattdessen ersetzen Sie diese durch eine eigene `UpdateRegistry`\-Methode, die [CAtlModule::UpdateRegistryFromResourceD](../Topic/CAtlModule::UpdateRegistryFromResourceD.md) oder [CAtlModule::UpdateRegistryFromResourceS](../Topic/CAtlModule::UpdateRegistryFromResourceS.md) aufruft, und führen Sie das Array **\_ATL\_REGMAP\_ENTRY**\-Strukturen.  Das Array von **\_ATL\_REGMAP\_ENTRY** muss mindestens einen Eintrag verfügen, dem **NULL**{,}**NULL** festgelegt wird, und dieser Eintrag sollte der letzte Eintrag immer sein.  Andernfalls wird ein Zugriffsverletzungsfehler generiert, wenn **UpdateRegistryFromResource** aufgerufen wird.  
  
> [!NOTE]
>  Wenn es ein Projekt erstellt, das eine ausführbare Datei ausgibt, fügt ATL automatisch Anführungszeichen um den Pfadnamen hinzu, der zur Laufzeit mit dem **%MODULE%** Registrierungsstellenskriptparameter erstellt wird.  Wenn Sie den Pfadnamen die keine Anführungszeichen enthalten soll, verwenden Sie den neuen **%MODULE\_RAW%**\-Parameter stattdessen.  
>   
>  Wenn ein Projekt erstellt, das ein DLL ausgibt, fügt ATL Anführungszeichen nicht den Pfadnamen hinzu, wenn **%MODULE%** oder **%MODULE\_RAW%** verwendet wird.  
  
## Siehe auch  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)