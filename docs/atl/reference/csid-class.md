---
title: "CSid Class"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CSid"
  - "ATL::CSid"
  - "ATL.CSid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSid class"
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CSid Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist ein Wrapper für eine Struktur `SID` \(Sicherheits\-ID\).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CSid  
  
```  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CSid::CSidArray](../Topic/CSid::CSidArray.md)|Ein Array von `CSid`\-Objekten.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSid::CSid](../Topic/CSid::CSid.md)|Der \-Konstruktor.|  
|[CSid::~CSid](../Topic/CSid::~CSid.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSid::AccountName](../Topic/CSid::AccountName.md)|Gibt den Namen des Kontos zurück, das mit dem `CSid`\-Objekt zugeordnet ist.|  
|[CSid::Domain](../Topic/CSid::Domain.md)|Gibt den Namen der Domäne zurück, die dem `CSid`\-Objekt zugeordnet ist.|  
|[CSid::EqualPrefix](../Topic/CSid::EqualPrefix.md)|Testet `SID` \(Sicherheits\-ID\)\-Präfixe auf Gleichheit.|  
|[CSid::GetLength](../Topic/CSid::GetLength.md)|Gibt die Länge des `CSid`\-Objekts zurück.|  
|[CSid::GetPSID](../Topic/CSid::GetPSID.md)|Gibt einen Zeiger auf eine Struktur `SID` zurück.|  
|[CSid::GetPSID\_IDENTIFIER\_AUTHORITY](../Topic/CSid::GetPSID_IDENTIFIER_AUTHORITY.md)|Gibt einen Zeiger auf die **SID\_IDENTIFIER\_AUTHORITY**\-Struktur zurück.|  
|[CSid::GetSubAuthority](../Topic/CSid::GetSubAuthority.md)|Gibt ein bestimmtes subauthority in einer **SID** \-Struktur zurück.|  
|[CSid::GetSubAuthorityCount](../Topic/CSid::GetSubAuthorityCount.md)|Gibt die Anzahl subauthority zurück.|  
|[CSid::IsValid](../Topic/CSid::IsValid.md)|Testet das `CSid`\-Objekt Gültigkeit.|  
|[CSid::LoadAccount](../Topic/CSid::LoadAccount.md)|Aktualisiert das `CSid`\-Objekt, das den Kontonamen und die Domäne angegeben werden, oder eine vorhandene `SID`\-Struktur.|  
|[CSid::Sid](../Topic/CSid::Sid.md)|Gibt die ID\-Zeichenfolge zurück.|  
|[CSid::SidNameUse](../Topic/CSid::SidNameUse.md)|Gibt eine Beschreibung des Zustands des `CSid`\-Objekts zurück.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator \=](../Topic/CSid::operator%20=.md)|Zuweisungsoperator|  
|[Operator const SID \*](../Topic/CSid::operator%20const%20SID%20*.md)|Wandelt ein `CSid`\-Objekt in einen Zeiger auf eine Struktur `SID` um.|  
  
### Globale Operatoren  
  
|||  
|-|-|  
|[Operator \=\=](../Topic/CSid::operator%20==.md)|Tests zwei Sicherheitsbeschreibungsobjekte für Gleichheit|  
|[Operator\! \=](../Topic/CSid::operator%20!=.md)|Tests zwei Sicherheitsbeschreibungsobjekte für Ungleichheit|  
|[Operator \<](../Topic/CSid::operator%20%3C.md)|Vergleicht relativen Wert zweier Sicherheitsbeschreibungsobjekten.|  
|[Operator \>](../Topic/CSid::operator%20%3E.md)|Vergleicht relativen Wert zweier Sicherheitsbeschreibungsobjekten.|  
|[Operator \<\=](../Topic/CSid::operator%20%3C=.md)|Vergleicht relativen Wert zweier Sicherheitsbeschreibungsobjekten.|  
|[Operator \>\=](../Topic/CSid::operator%20%3E=.md)|Vergleicht relativen Wert zweier Sicherheitsbeschreibungsobjekten.|  
  
## Hinweise  
 Die `SID`\-Struktur ist eine Struktur mit variabler Länge, die verwendet wird, um Benutzer oder Gruppen eindeutig zu identifizieren.  
  
 Anwendungen müssen die `SID`\-Struktur nicht direkt ändern, aber verwenden stattdessen die Methoden, die in dieser Wrapperklasse bereitgestellt werden.  Siehe auch [AtlGetOwnerSid](../Topic/AtlGetOwnerSid.md), [AtlSetGroupSid](../Topic/AtlSetGroupSid.md), [AtlGetGroupSid](../Topic/AtlGetGroupSid.md) und [AtlSetOwnerSid](../Topic/AtlSetOwnerSid.md).  
  
 Eine Einführung in Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Anforderungen  
 **Header:** atlsecurity.h  
  
## Siehe auch  
 [Beispiel für die Sicherheit](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)   
 [Operators Alphabetical Reference](../../atl/reference/atl-operators.md)