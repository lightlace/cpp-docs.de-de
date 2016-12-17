---
title: "Vorlagendirektiven"
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
  - "[!else] (Vorlagendirektive)"
  - "[!endif] (Vorlagendirektive)"
  - "[!endloop] (Vorlagendirektive)"
  - "[!if] (Vorlagendirektive)"
  - "[!loop] (Vorlagendirektive)"
  - "[!output] (Vorlagendirektive)"
  - "Benutzerdefinierte Assistenten, Vorlagendirektiven"
  - "Direktiven, Vorlagendirektiven"
  - "else-Direktive ([!else])"
  - "endif-Direktive ([!endif])"
  - "endloop-Direktive ([!endloop])"
  - "if-Direktive ([!if])"
  - "loop-Direktive ([!loop])"
  - "output-Direktive ([!output])"
  - "Vorlagendirektiven"
ms.assetid: b6204153-813a-423c-b044-e39c352cc5af
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Vorlagendirektiven
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können die folgenden Vorlagendirektiven in der [Vorlagendatei](../ide/template-files.md) eines Assistenten sowie in der [Datei "Templates.inf"](../ide/templates-inf-file.md) verwenden, um den Assistenten anzupassen.  
  
|Direktive|Beschreibung|  
|---------------|------------------|  
|\[\!  if \]|Leitet eine Programmverzweigung zum Überprüfen einer Bedingung ein.|  
|\[\!  else \]|Teil der \[\!  if \]\-Programmverzweigung.  Überprüft auf eine weitere Bedingung.|  
|\[\!  endif \]|Beendet die Definition einer \[\!  if \]\-Programmverzweigung.|  
|\[\!  output \]|Kann in zwei Weisen verwendet werden:<br /><br /> -   \[\!  output "Zeichenfolge" \] gibt die Zeichenfolge aus.<br />-   \[\!  output SYMBOL\_STRING \] gibt den Wert des Symbols SYMBOL\_STRING aus.|  
|\[\!  loop \]|Kann in zwei Weisen verwendet werden:<br /><br /> -   \[\!  loop \= 5 \]<br />-   \[\!  loop \= *ANZ\_SEITEN* \] wobei *ANZ\_SEITEN* ein Symbol mit einem numerischen Wert darstellt.|  
|\[\!  endloop \]|Beendet eine Schleifenstruktur.|  
  
 Durch die linke eckige Klammer \(\[\), auf die unmittelbar ein Ausrufezeichen \(\!\) folgt, wird der Anfang einer Vorlagendirektive gekennzeichnet.  Durch die rechte eckige Klammer wird das Ende einer Vorlagendirektive gekennzeichnet.  Im Folgenden die erforderliche Syntax:  
  
```  
[!directive params]  
```  
  
 Lediglich zwischen *directive* und *params* ist ein Leerzeichen oder ein Zeichen, das keinen Bezeichner darstellt, erforderlich.  
  
## Beispiel  
  
```  
[!if SAMPLE_RADIO_OPTION1]  
You have checked the option 'Sample radio button option 1'  
[!else]  
You have checked the option 'Sample radio button option 2'  
[!endif]  
```  
  
 Mit den oben beschriebenen Direktiven können Sie in einer Vorlagendatei die folgenden Operatoren verwenden.  
  
```  
+  
-     
=  
!=     
==     
||     
&&    
!  
```  
  
## Beispiel  
  
```  
[!if SYMBOL_STRING != 0]  
```  
  
## Siehe auch  
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)