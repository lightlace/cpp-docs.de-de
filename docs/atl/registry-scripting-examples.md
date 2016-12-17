---
title: "Registry Scripting Examples"
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
  - "registrar scripts [ATL]"
  - "Registrierung, Registrar"
  - "Erstellen von Skripts, Beispiele"
  - "Skripts, Registrar scripts"
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Registry Scripting Examples
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Beispielskripte in diesem Thema zeigen, wie ein Schlüssel der Systemregistrierung hinzugefügt wird, registriert den Registrierungsstellen\-COM\-Server und geben mehrere Analysestrukturen an.  
  
## Fügen Sie einen Schlüssel HKEY\_CURRENT\_USER hinzu  
 Die folgenden Analysestruktur zeigt ein einfaches Skript, das eine einzelne Schlüssel der Systemregistrierung hinzugefügt wird.  Insbesondere wird das Skript die Schlüssel, `MyVeryOwnKey`, `HKEY_CURRENT_USER` hinzu.  Sie weist auch den Standardzeichenfolgenwert von `HowGoesIt?` zur neuen Schlüssel zu:  
  
```  
HKEY_CURRENT_USER  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
```  
  
 Dieses Skript kann problemlos erweitert werden, um mehrere Unterschlüssel zu definieren, wie folgt:  
  
```  
HKCU  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
   {  
      'HasASubkey'  
      {  
         'PrettyCool?' = d '55'  
         val 'ANameValue' = s 'WithANamedValue'  
      }  
   }  
}  
```  
  
 Jetzt wird das Skript einen Unterschlüssel, `HasASubkey`, `MyVeryOwnKey` hinzu.  Zu diesem Unterschlüssel fügt es den `PrettyCool?` Unterschlüssel \(mit einem Standard `DWORD`\-Wert 55\) und benannte `ANameValue`\-Wert hinzu \(mit einem Zeichenfolgenwert von `WithANamedValue`\).  
  
##  <a name="_atl_register_the_registrar_com_server"></a> Registrieren Sie den Registrierungsstellen\-COM\-Server  
 Das folgende Skript registriert den Registrierungsstellen\-COM\-Server selbst.  
  
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
  
 Zur Laufzeit wird diese Analysestruktur die `ATL.Registrar` Schlüssel `HKEY_CLASSES_ROOT` hinzu.  So dieser neuen Schlüssel anschließend:  
  
-   Gibt `ATL Registrar Class` als Standard Zeichenfolgenwert der Schlüssel an.  
  
-   Fügt `CLSID` als Unterschlüssel hinzu.  
  
-   Gibt `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` für `CLSID` an.  \(Dieser Wert ist die CLSID der Registrierungsstelle zur Verwendung mit `CoCreateInstance`.\)  
  
 Da `CLSID` freigegeben wird, sollte es nicht in entfernt werden Registrierung aufhebt Modus.  Die Anweisung, `NoRemove CLSID`, erfolgt, indem sie dieses `CLSID` angibt, muss im Registermodus geöffnet und in ignoriert wurde heben Sie Modus Registrierung auf.  
  
 Vor der Neuerstellung der Schlüssel die `ForceRemove`\-Anweisung stellt eine organisatorische Aufgabe aus dem Entfernen einer Schlüssel und der aller dessen Unterschlüssel bereit.  Dies kann hilfreich sein, wenn die Namen der Unterschlüssel geändert haben.  In diesem Beispielskript `ForceRemove` überprüft, um festzustellen, ob `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` bereits vorhanden ist.  Wenn ja, `ForceRemove`:  
  
-   Löscht rekursiv `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` und alle seine Unterschlüssel.  
  
-   Erstellt `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` neu.  
  
-   Fügt `ATL Registrar Class` als Standard Zeichenfolgenwert für `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` hinzu.  
  
 Die Analysestruktur werden nun zwei neue Unterschlüssel `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` hinzu.  Der erste Schlüssel, `ProgID`, ruft einen Standardzeichenfolgenwert ab, der die ProgID ist.  Die zweite Schlüssel, `InprocServer32`, ruft einen Zeichenfolgenwert, `%MODULE%`, der ein Präprozessorwert ist, der im Abschnitt beschrieben wird, [Verwenden von ersetzbaren Parameter \(der Präprozessor der Registrierungsstelle\)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md), dieses Artikels ab.  `InprocServer32` ruft auch einen benannten Wert, `ThreadingModel`, mit einem Zeichenfolgenwert von `Apartment` ab.  
  
## Geben Sie mehrere Analyse\-Strukturen an  
 Um mehr als eine Analysestruktur in einem Skript anzugeben, fügen Sie einfach eine Struktur am Ende von anderen.  Beispielsweise fügt das folgende Skript die Schlüssel, `MyVeryOwnKey`, den Analysestrukturen für `HKEY_CLASSES_ROOT` und `HKEY_CURRENT_USER` hinzu:  
  
```  
HKCR  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
HKEY_CURRENT_USER  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
```  
  
> [!NOTE]
>  In einem Registrierungsstellenskript ist 4K die maximale Scheingröße.  \(A\-Token erkennbare ist jedes Element in der Syntax.\) Im vorherigen Beispielskript sind `HKCR`, `HKEY_CURRENT_USER`, `'MyVeryOwnKey'` und `'HowGoesIt?'` alle Token.  
  
## Siehe auch  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)