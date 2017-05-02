---
title: "Map::MapChanged-Ereignis | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::MapChanged"
ms.assetid: d14b5b93-36ff-47a5-b588-dd1dc6ea4364
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::MapChanged-Ereignis
Wird ausgelöst, wenn ein Element in eine Zuordnung eingefügt bzw. aus der Zuordnung entfernt wird.  
  
## Syntax  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
## Eigenschaftswert\/Rückgabewert  
 Ein [MapChangedEventHandler\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br206644.aspx), der Informationen zum Objekt enthält, das das Ereignis ausgelöst hat, sowie die Art der Änderung, die aufgetreten ist. Siehe auch [IMapChangedEventArgs\<K\>](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) und [CollectionChange\-Enumeration](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).  
  
## .NET Framework-Entsprechung  
 Windows Store\-Apps, die für ein C\#\- oder Visual Basic\-Projekt IMap\<K,V\> als IDictionary\<K,V\> verwenden.  
  
## Anforderungen  
 Windows 8.0 oder höher  
  
## Siehe auch  
 [Auflistungen](../cppcx/collections-c-cx.md)