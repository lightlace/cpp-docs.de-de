---
title: Registrierung Skriptbeispielen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6dc28d8a0d5dc24d0f0c665e5a17fc38e0c9d08f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753148"
---
# <a name="registry-scripting-examples"></a>Beispiele für die Registrierungsskripterstellung

Skript in diesem Thema wird gezeigt, wie fügen Sie einen Schlüssel in die systemregistrierung, registrieren Sie den Registrierungsstelle COM-Server und mehrere analysestrukturen angeben.

## <a name="add-a-key-to-hkeycurrentuser"></a>Fügen Sie einen Schlüssel in HKEY_CURRENT_USER

Die folgenden Analysestruktur veranschaulicht ein einfaches Skript, das einen einzelnen Schlüssel in die systemregistrierung hinzufügt. Insbesondere das Skript fügt den Schlüssel `MyVeryOwnKey`zu `HKEY_CURRENT_USER`. Außerdem weist den Standardwert des `HowGoesIt` auf den neuen Schlüssel:

```  
HKEY_CURRENT_USER  
{  
'MyVeryOwnKey' = s 'HowGoesIt'  
}  
```

Dieses Skript kann problemlos erweitert werden, um mehrere Unterschlüssel wird wie folgt definieren:

```  
HKCU  
{  
    'MyVeryOwnKey' = s 'HowGoesIt'  
    {  
        'HasASubkey'  
        {  
            'PrettyCool' = d '55'  
            val 'ANameValue' = s 'WithANamedValue'  
        }  
    }  
}  
```

Nun, das Skript fügt einen Unterschlüssel, `HasASubkey`zu `MyVeryOwnKey`. Unterschlüssel, fügt es sowohl den `PrettyCool` Unterschlüssel (hat den Standardwert `DWORD` Wert von 55) und die `ANameValue` benannten Wert (mit einem Zeichenfolgenwert des `WithANamedValue`).

##  <a name="_atl_register_the_registrar_com_server"></a> Die Registrierungsstelle COM-Server registrieren

Das folgende Skript registriert den Registrierungsstelle COM-Server selbst.

```  
HKCR  
{  
    ATL.Registrar = s 'ATL Registrar Class'  
    {  
        CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'  
    }  
    NoRemove CLSID  
    {  
        ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = s 'ATL Registrar Class'  
        {  
            ProgID = s 'ATL.Registrar'  
            InprocServer32 = s '%MODULE%'  
            {  
                val ThreadingModel = s 'Apartment'  
            }  
        }  
    }  
}  
```

Bei der Ausführung dieser Analysestruktur fügt die `ATL.Registrar` um `HKEY_CLASSES_ROOT`. In diesem neuen Schlüssel klicken Sie dann die It:

- Gibt an, `ATL Registrar Class` als Standard-Zeichenfolgenwert des Schlüssels.

- Fügt `CLSID` als einen Unterschlüssel.

- Gibt an, `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` für `CLSID`. (Dieser Wert ist der Registrierungsstelle die CLSID für die Verwendung mit `CoCreateInstance`.)

Da `CLSID` wird freigegeben, er sollte nicht entfernt werden in der Aufhebung der Registrierung. Die Anweisung `NoRemove CLSID`, gibt an, dass Sie hierfür `CLSID` im Register-Modus geöffnet und in die Aufhebung der Registrierung ignoriert werden sollten.

Die `ForceRemove` Anweisung bietet eine organisatorische-Funktion entfernen, indem ein Schlüssel und alle seine Unterschlüssel vor dem erneuten Erstellen des Schlüssels. Dies kann nützlich sein, wenn die Namen der Unterschlüssel geändert haben. In diesem Beispiel scripting `ForceRemove` überprüft, ob `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` ist bereits vorhanden. Wenn dies der Fall, `ForceRemove`:

- Rekursiv löscht `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` und alle seine Unterschlüssel.

- Neu erstellt `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.

- Fügt `ATL Registrar Class` als den Standardwert für `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.

Die Analysestruktur bietet nun zwei neue Unterschlüssel `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`. Der erste Schlüssel, `ProgID`, ruft Sie einen Standardwert für die Zeichenfolge, die die ProgID ist. Der zweite Schlüssel, `InprocServer32`, einen Standardwert für die Zeichenfolge, ruft `%MODULE%`, d. h. ein Präprozessor Wert erläutert wird, klicken Sie im Abschnitt [mithilfe von ersetzbaren Parametern (der Registrierungspräprozessor)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md), dieses Artikels. `InprocServer32` Ruft auch einen benannten Wert `ThreadingModel`, mit einem Zeichenfolgenwert des `Apartment`.

## <a name="specify-multiple-parse-trees"></a>Geben Sie mehrere in Analysestrukturen

Um mehr als eine Analysestruktur in einem Skript anzugeben, fügen Sie eine Struktur einfach am Ende eines anderen. Das folgende Skript fügt beispielsweise den Schlüssel, `MyVeryOwnKey`, um die analysestrukturen für beide `HKEY_CLASSES_ROOT` und `HKEY_CURRENT_USER`:

```  
HKCR  
{  
    'MyVeryOwnKey' = s 'HowGoesIt'  
}  
HKEY_CURRENT_USER  
{  
    'MyVeryOwnKey' = s 'HowGoesIt'  
}  
```

> [!NOTE]
> In einem Skript Registrierungsstelle beträgt 4 KB für die maximale Größe des Tokens. (Ein Token ist erkennbare Element in der Syntax.) Im vorherigen Beispiel scripting `HKCR`, `HKEY_CURRENT_USER`, `'MyVeryOwnKey'`, und `'HowGoesIt'` alle Token werden.

## <a name="see-also"></a>Siehe auch

[Erstellen von Registrierungsskripts](../atl/creating-registrar-scripts.md)

