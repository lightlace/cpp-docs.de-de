---
title: "/SECTION (EDITBIN)"
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
  - "/section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SECTION (editbin-Option)"
  - "Ausrichtungszeichen in Abschnitten"
  - "SECTION (editbin-Option)"
  - "-SECTION (editbin-Option)"
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /SECTION (EDITBIN)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SECTION:name[=newname][,attributes][alignment]  
```  
  
## Hinweise  
 Durch diese Option werden die Attribute eines Abschnitts geändert, wobei die Attribute überschrieben werden, die während der Kompilierung oder der Verknüpfung der Objektdatei für den Abschnitt festgelegt wurden.  
  
 Nach dem Doppelpunkt \( **:** \) wird der Name des Abschnitts angegeben.  Um den Abschnittsnamen zu ändern, geben Sie hinter dem Namen \(*name*\) ein Gleichheitszeichen \(\=\) und einen neuen Namen \(*newname*\) für den Abschnitt ein.  
  
 Um für den Abschnitt `attributes` festzulegen oder zu ändern, geben Sie ein Komma \(**,**\), gefolgt von einem oder mehreren Attributzeichen ein.  Um ein Attribut zu negieren, setzen Sie vor das Zeichen ein Ausrufezeichen \(\!\).  Die nachfolgenden Zeichen stellen Speicherattribute dar:  
  
|Attribute|Einstellung|  
|---------------|-----------------|  
|c|Code|  
|d|discardable|  
|e|executable|  
|i|initialized data|  
|k|cached virtual memory|  
|m|link remove|  
|o|link info|  
|p|paged virtual memory|  
|r|read|  
|s|shared|  
|u|uninitialized data|  
|w|write|  
  
 Um *alignment* zu steuern, geben Sie das Zeichen **A**, gefolgt von einem Zeichen ein, mit dem Sie wie folgt die Größe der Ausrichtung in Bytes festlegen:  
  
|Zeichen|Ausrichtungsgröße in Bytes|  
|-------------|--------------------------------|  
|1|1|  
|2|2|  
|4|4|  
|8|8|  
|p|16|  
|t|32|  
|s|64|  
|x|keine Ausrichtung|  
  
 Geben Sie die Zeichen für `attributes` und *alignment* als eine Zeichenfolge ohne Leerraum an.  Bei diesen Zeichen wird keine Groß\-\/Kleinschreibung berücksichtigt.  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)