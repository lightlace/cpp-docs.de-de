---
title: "Attribute Contexts"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], contexts"
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Attribute Contexts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+\-Attribute können mithilfe von vier grundlegenden Felder beschrieben werden: Sie können das Ziel übernommen wurden \(**Gilt für**\), wenn sie**Wiederholbar**\) oder nicht \(wiederholbar sind, das erforderliche Vorhandensein anderer Attribute \(**Erforderliche Attribute**\) und Inkompatibilitäten mit anderen Attributen \(**Ungültige Attribute**\).  Diese Felder werden in einer Begleittafel im Referenzthema jedes Attributs aufgelistet.  Jedes dieser Felder wird im Folgenden beschrieben.  
  
## Gilt für  
 Dieses Feld beschreibt die verschiedenen C\+\+\-Sprachelemente, die gültige Ziele für das angegebene Attribut sind.  Wenn beispielsweise ein Attribut „Klasse“ auf dem **Gilt für** Feld angegeben wird, gibt dieses an, dass das Attribut nur auf eine gültige C\+\+\-Klasse angewendet werden kann.  Wenn das Attribut auf eine Memberfunktion einer Klasse angewendet wird, wird ein Syntaxfehler auftreten.  
  
 Weitere Informationen finden Sie unter [Verwendung von Attributen](../windows/attributes-by-usage.md).  
  
## Wiederholbar  
 Dieses Feld gibt an, ob das Attribut auf dasselbe Ziel wiederholt angewendet werden kann.  Die meisten Attribute sind nicht wiederholbar.  
  
## Erforderliche Attribute  
 Dieses Feldlisten andere Attribute, die vorhanden sein müssen \(das heißt auf dasselbe Ziel angewendet\) für das angegebene Attribut ordnungsgemäß funktioniert.  Es ist nur selten für ein Attribut, alle Einträge für dieses Feld verfügen.  
  
## Ungültige Attribute  
 Dieses Feldlisten andere Attribute, die dem angegebenen Attribut nicht kompatibel sind.  Es ist nur selten für ein Attribut, alle Einträge für dieses Feld verfügen.  
  
## Siehe auch  
 [C\+\+ Attributes Reference](../windows/cpp-attributes-reference.md)