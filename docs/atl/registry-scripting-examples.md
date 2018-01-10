---
title: Registrierung Skriptbeispielen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1b2a5dfd3bd31674917a5b41174277ef787aff25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="registry-scripting-examples"></a>Beispiele für die Registrierung Scripting
Skripts in diesem Thema wird erklärt, wie fügen Sie einen Schlüssel in der systemregistrierung, registrieren Sie den Registrierungsstelle COM-Server und mehrere Analyse Strukturen angeben.  
  
## <a name="add-a-key-to-hkeycurrentuser"></a>Fügen Sie einen Schlüssel in HKEY_CURRENT_USER  
 Die folgenden Analysestruktur zeigt ein einfaches Skript, das einen einzelnen Schlüssel in der systemregistrierung hinzufügt. Insbesondere das Skript fügt den Schlüssel `MyVeryOwnKey`in `HKEY_CURRENT_USER`. Außerdem weist er den Standard-Zeichenfolgenwert des `HowGoesIt` auf den neuen Schlüssel:  
  
```  
HKEY_CURRENT_USER  
{  
 'MyVeryOwnKey' = s 'HowGoesIt'  
}  
```  
  
 Dieses Skript kann leicht erweitert werden, um mehrere Unterschlüssel wie folgt definieren:  
  
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
  
 Das Skript fügt nun einen Unterschlüssel `HasASubkey`in `MyVeryOwnKey`. Unterschlüssel, fügt er sowohl die `PrettyCool` Unterschlüssel (hat den Standardwert `DWORD` Wert von 55) und die `ANameValue` benannten Wert (mit einem Zeichenfolgenwert von `WithANamedValue`).  
  
##  <a name="_atl_register_the_registrar_com_server"></a>Registrieren Sie den Registrierungsstelle COM-Server  
 Das folgende Skript registriert die Registrierungsstelle COM-Server selbst.  
  
```  
HKCR  
{  
    ATL.Registrar = s 'ATL Registrar Class'  
 {  
    CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'  
 }  
    NoRemove CLSID  
 {  
    ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = 
    s 'ATL Registrar Class'  
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
  
 Zur Laufzeit wird dieser Analysestruktur fügt die `ATL.Registrar` um `HKEY_CLASSES_ROOT`. In diesem neuen Schlüssel dann It:  
  
-   Gibt an, `ATL Registrar Class` als Standard-Zeichenfolgenwert des Schlüssels.  
  
-   Fügt `CLSID` als einen Unterschlüssel.  
  
-   Gibt an, `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` für `CLSID`. (Dieser Wert ist der Registrierungsstelle CLSID für die Verwendung mit `CoCreateInstance`.)  
  
 Da `CLSID` wird freigegeben, es sollte nicht entfernt werden im Modus für Registrierung aufheben. Die Anweisung `NoRemove CLSID`, zeigt an, dass Sie hierfür `CLSID` im Modus für Registrierung geöffnet und im Modus für Registrierung ignoriert werden soll.  
  
 Die `ForceRemove` Anweisung bietet eine Housekeeping-Funktion entfernen, indem ein Schlüssel und alle seine Unterschlüssel vor dem erneuten Erstellen des Schlüssels. Dies kann nützlich sein, wenn die Namen der Unterschlüssel geändert wurden. In diesem Beispiel scripting `ForceRemove` überprüft, ob `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` ist bereits vorhanden. Wenn dies der Fall, `ForceRemove`:  
  
-   Löscht rekursiv `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` und alle seine Unterschlüssel.  
  
-   Neuerstellen `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
-   Fügt `ATL Registrar Class` als den Standardwert für `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
 Fügt die Analysestruktur nun zwei neue Unterschlüssel `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`. Der erste Schlüssel `ProgID`, ruft einen Standard-Zeichenfolgenwert, der die ProgID-Wert. Der zweite Schlüssel `InprocServer32`, ruft einen Standard-Zeichenfolgenwert `%MODULE%`, d. h. ein Präprozessor Wert erläutert wird, klicken Sie im Abschnitt [mithilfe von ersetzbaren Parametern (die Registrierungsstelle Präprozessor)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md), dieses Artikels. `InprocServer32`Ruft auch einen benannten Wert `ThreadingModel`, mit einem Zeichenfolgenwert von `Apartment`.  
  
## <a name="specify-multiple-parse-trees"></a>Geben Sie mehrere Parserstrukturen  
 Um mehr als eine Analysestruktur in ein Skript angeben, müssen platzieren Sie eine Struktur einfach am Ende eines anderen. Das folgende Skript fügt z. B. den Schlüssel `MyVeryOwnKey`, um die Analyse Strukturen für beide `HKEY_CLASSES_ROOT` und `HKEY_CURRENT_USER`:  
  
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
>  In einem Skript Registrierungsstelle beträgt 4 KB maximale Tokengröße. (Ein Token ist jedes erkennbare Element in der Syntax.) In der vorherigen Beispielskript `HKCR`, `HKEY_CURRENT_USER`, `'MyVeryOwnKey'`, und `'HowGoesIt'` werden alle Token.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Registrierungsskripts](../atl/creating-registrar-scripts.md)

