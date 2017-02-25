---
title: "Understanding Parse Trees | Microsoft Docs"
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
  - "parse trees"
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Understanding Parse Trees
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können eine oder mehrere Analysestrukturen im Registrierungsstellenskript definieren, in dem jede Analysestruktur die folgende Form aufweist:  
  
```  
<root key>{<registry expression>}+  
```  
  
 Dabei gilt:  
  
```  
<root key> ::=  HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |  
               HKEY_LOCAL_MACHINE | HKEY_USERS |  
               HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |  
               HKEY_CURRENT_CONFIG | HKCR | HKCU |  
               HKLM | HKU | HKPD | HKDD | HKCC  
<registry expression> ::= <Add Key> | <Delete Key>  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
              [<Key Value>][{< Add Key>}]  
<Delete Key> ::=  Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
>  `HKEY_CLASSES_ROOT` und `HKCR` sind äquivalent; `HKEY_CURRENT_USER` und `HKCU` sind äquivalent; u. a.  
  
 Eine Analysestruktur kann mehrere Schlüssel und Unterschlüssel \<root key\>hinzufügen.  Auf diese Weise enthält sie das Handle eines Unterschlüssels geöffnet, bis der Parser Analysieren alle Unterschlüssel abgeschlossen hat.  Dieser Ansatz ist effizienter als weiter auf einer einzelnen Schlüssel jeweils, wie im folgenden Beispiel gezeigt:  
  
```  
HKEY_CLASSES_ROOT  
{  
   'MyVeryOwnKey'  
   {  
      'HasASubKey'  
      {  
         'PrettyCool?'  
      }  
   }  
}  
```  
  
 Hier wird die Registrierungsstelle zuerst geöffnet \(erstellt\), `HKEY_CLASSES_ROOT\MyVeryOwnKey`.  Es sieht dann, dass `MyVeryOwnKey` einen Unterschlüssel hat.  Anstatt schließen Sie die Schlüssel zu `MyVeryOwnKey` Registrierungsstelle beibehält, die das Handle und öffnet \(erstellt\), `HasASubKey` mit diesem Elementen Handles.  \(Die Systemregistrierung kann langsamer sein, wenn kein übergeordnetes Handle geöffnet ist\). Daher ist `HKEY_CLASSES_ROOT\MyVeryOwnKey` zu öffnen und `HasASubKey` mit `MyVeryOwnKey` als übergeordnetes Element öffnen schneller als, `MyVeryOwnKey` Öffnen, Schließen `MyVeryOwnKey`, und `MyVeryOwnKey\HasASubKey` dann, Öffnen.  
  
## Siehe auch  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)