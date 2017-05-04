---
title: "Platform::Agile-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile"
ms.assetid: e34459a9-c429-4c79-97fd-030c43ca4155
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Agile-Klasse
Stellt ein Objekt dar, das über „MashalingBehavior\=Standard“ als Agile\-Objekt verfügt, das die Chancen für Threadingausnahmen zur Laufzeit erheblich verringert.`Agile<T>` ermöglicht es dem Nicht\-Agile\-Objekt, denselben oder einen anderen Thread aufzurufen oder von diesem aufgerufen zu werden. Weitere Informationen finden Sie unter [Threading und Marshalling](../cppcx/threading-and-marshaling-c-cx.md).  
  
## Syntax  
  
```scr  
  
template <typename T>  
    class Agile  
;  
```  
  
#### Parameter  
 T  
 Der Typname für die Nicht\-Agile\-Klasse.  
  
## Hinweise  
 Die meisten Klassen in der [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] sind agil. Ein Agile\-Objekt kann ein „in\-proc“\- oder „out\-of\-proc“\-Objekt in demselben oder einem anderen Thread aufrufen oder von diesem aufgerufen werden. Wenn es sich nicht um ein Agile\-Objekt handelt, schließen Sie das Nicht\-Agile\-Objekt in ein `Agile<T>`\-Objekt ein, das agil ist. Dann kann das `Agile<T>`\-Objekt gemarshallt und das zugrunde liegende Nicht\-Agile\-Objekt verwendet werden.  
  
 Die `Agile<T>`\-Klasse ist eine systemeigene C\+\+\-Standardklasse und erfordert `agile.h`. Es stellt das Nicht\-Agile\-Objekt und den *Kontext* des Agile\-Objekts dar. Der Kontext gibt das Threadmodell und Marshallingverhalten eines Agile\-Objekts an. Das Betriebssystem verwendet den Kontext, um zu ermitteln, wie ein Objekt gemarshallt wird.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[Agile::Agile\-Konstruktor](../cppcx/agile-agile-constructor.md)|Initialisiert eine neue Instanz der Agile\-Klasse.|  
|[Agile::~Agile\-Destruktor](../cppcx/agile-tilde-agile-destructor.md)|Zerstört die aktuelle Instanz der Agile\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[Agile::Get](../cppcx/agile-get-method.md)|Gibt den Handle auf das Objekt zurück, das vom aktuellen Agile\-Objekt dargestellt wird.|  
|[Agile::GetAddressOf](../cppcx/agile-getaddressof-method.md)|Initialisiert das aktuelle Agile\-Objekt neu und gibt dann die Adresse eines Handles für ein Objekt vom Typ `T` zurück.|  
|[Agile::GetAddressOfForInOut](../cppcx/agile-getaddressofforinout-method.md)|Gibt die Adresse eines Handles zum Objekt zurück, das vom aktuellen Agile\-Objekt dargestellt wird.|  
|[Agile::Release](../cppcx/agile-release-method.md)|Verwirft das Objekt und den Kontext, die dem aktuellen Agile\-Objekt zugrunde liegen.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[Agile::operator\-\>](../cppcx/agile-operator-arrow-operator.md)|Ruft ein Handle auf das Objekt ab, das vom aktuellen Agile\-Objekt dargestellt wird.|  
|[Agile::operator\=](../cppcx/agile-operator-assign-operator.md)|Weist dem aktuellen Agile\-Objekt den angegebenen Wert zu.|  
  
## Vererbungshierarchie  
 `Object`  
  
 `Agile`  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** agile.h  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)