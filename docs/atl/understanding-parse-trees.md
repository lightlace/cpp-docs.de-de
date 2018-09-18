---
title: ATL-Registrierung und in Analysestrukturen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08c92d86cbbfd38ed4ae852ce52e3b70735812e9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028089"
---
# <a name="understanding-parse-trees"></a>Einführung in Analysestrukturen

Sie können eine oder mehrere in analysestrukturen in Ihrem Skript Registrierungsstelle definieren, in dem jede Analysestruktur die folgende Form aufweist:

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
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name> [<Key Value>][{<Add Key>}]
<Delete Key> ::= Delete<Key Name>
<Key Name> ::= '<AlphaNumeric>+'
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0
<Key Value> ::== <Key Type><Key Name>
<Key Type> ::= s | d
<Key Value> ::= '<AlphaNumeric>'
```

> [!NOTE]
> `HKEY_CLASSES_ROOT` und `HKCR` entsprechen; `HKEY_CURRENT_USER` und `HKCU` sind einander entsprechen und so weiter.

Eine Analysestruktur kann mehrere Schlüssel und Unterschlüssel zum Hinzufügen der \<Stammschlüssel >. Auf diese Weise bleibt es Handle des Unterschlüssels geöffnet, bis der Parser alle seine Unterschlüssel Analyse abgeschlossen wurde. Dieser Ansatz ist effizienter als das Betriebssystem auf einem einzelnen Schlüssel zu einem Zeitpunkt, wie im folgenden Beispiel gezeigt:

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

Hier zunächst die Registrierungsstelle wird geöffnet (erstellt) `HKEY_CLASSES_ROOT\MyVeryOwnKey`. Klicken Sie dann erkennt, dass `MyVeryOwnKey` verfügt über einen Unterschlüssel. Anstatt schließen Sie die Taste, um `MyVeryOwnKey`, die Registrierungsstelle behält das Handle und öffnet (erstellt) `HasASubKey` mithilfe dieses übergeordnete Handle. (Die Registrierung des Systems kann langsamer sein, wenn keine übergeordnete Handle geöffnet ist.) Öffnen Sie daher `HKEY_CLASSES_ROOT\MyVeryOwnKey` und öffnen Sie anschließend `HasASubKey` mit `MyVeryOwnKey` wie das übergeordnete Element schneller als das öffnendes ist `MyVeryOwnKey`schließen `MyVeryOwnKey`, und öffnen Sie anschließend `MyVeryOwnKey\HasASubKey`.

## <a name="see-also"></a>Siehe auch

[Erstellen von Registrierungsskripts](../atl/creating-registrar-scripts.md)

