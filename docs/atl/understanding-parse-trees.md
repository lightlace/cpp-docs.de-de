---
title: ATL-Registrierung und Analyse Strukturen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8ce648a541f6e0e2d4fac2e6ee19226e41f20ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-parse-trees"></a>Grundlegendes zur Analyse Strukturen
Sie können mindestens ein Analyse-Strukturen in Ihrem Skript Registrierungsstelle definieren, in dem jede Analysestruktur die folgende Form aufweist:  
  
```  
<root key>{<registry expression>}+  
```  
  
 Dabei gilt:  
  
```  
<root key> ::= HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |  
    HKEY_LOCAL_MACHINE | HKEY_USERS |  
    HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |  
    HKEY_CURRENT_CONFIG | HKCR | HKCU |  
    HKLM | HKU | HKPD | HKDD | HKCC  
<registry expression> ::= <Add Key> | <Delete Key>  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
 [<Key Value>][{<Add Key>}]  
<Delete Key> ::= Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
> `HKEY_CLASSES_ROOT`und `HKCR` gleichwertig; `HKEY_CURRENT_USER` und `HKCU` sind gleichwertig; und so weiter.  
  
 Eine Analysestruktur kann mehrere Schlüssel und Unterschlüssel zum Hinzufügen der \<Stammschlüssels >. In diesem Fall bleibt es einen Unterschlüssel Handle geöffnet, bis der Parser alle seine Unterschlüssel Analyse abgeschlossen wurde. Dieser Ansatz ist effizienter als das Arbeiten mit jeweils eines einzelnen Schlüssels, wie im folgenden Beispiel dargestellt:  
  
```  
HKEY_CLASSES_ROOT  
{  
 'MyVeryOwnKey'  
 {  
 'HasASubKey'  
 {  
 'PrettyCool'  
 }  
 }  
}  
```  
  
 Hier wird die Registrierungsstelle öffnet (erstellt) `HKEY_CLASSES_ROOT\MyVeryOwnKey`. Klicken Sie dann erkennt, dass `MyVeryOwnKey` einen Unterschlüssel verfügt. Anstatt schließen Sie die Taste, um `MyVeryOwnKey`, die Registrierungsstelle behält das Handle und öffnet (erstellt) `HasASubKey` Verwendung dieses übergeordneten Handles. (Die systemregistrierung kann langsamer sein, wenn keine übergeordnete Handle geöffnet ist.) Öffnen Sie daher `HKEY_CLASSES_ROOT\MyVeryOwnKey` und dann öffnen `HasASubKey` mit `MyVeryOwnKey` wie das übergeordnete Element öffnen schneller ist `MyVeryOwnKey`schließen `MyVeryOwnKey`, und dann öffnen `MyVeryOwnKey\HasASubKey`.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Registrierungsskripts](../atl/creating-registrar-scripts.md)

