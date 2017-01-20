---
title: "Unterst&#252;tzen des Freethreadings im Anbieter"
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
  - "OLE DB-Anbieter, Multithread"
  - "Threading [C++], Anbieter"
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Unterst&#252;tzen des Freethreadings im Anbieter
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Alle OLE DB\-Anbieterklassen sind threadsicher, und die Registrierungseinträge werden entsprechend festgelegt.  Sie sollten Freethreading unterstützen, damit in Mehrbenutzersituationen eine hohe Leistung gewährleistet ist.  Damit der Anbieter threadsicher bleibt, müssen Sie sicherstellen, dass der Code ordnungsgemäß blockiert wird.  Sobald Daten geschrieben oder gespeichert werden, muss der Zugriff auf kritische Abschnitte blockiert werden.  
  
 Jedes OLE DB\-Anbietervorlagenobjekt verfügt über einen eigenen kritischen Abschnitt.  Um das Blockieren zu erleichtern, sollte jede neu erstellte Klasse eine Vorlagenklasse sein, die den Namen der übergeordneten Klasse als Argument annimmt.  
  
 Im folgenden Beispiel wird das Blockieren von Code veranschaulicht:  
  
```  
template <class T>  
class CMyObject<T> : public...  
  
HRESULT MyObject::MyMethod(void)  
{  
   T* pT = (T*)this;      // this gets the parent class   
  
// You don't need to do anything if you are only reading information  
  
// If you want to write information, do the following:  
   pT->Lock();         // engages critical section in the object  
   ...;                // write whatever information you wish  
   pT->Unlock();       // disengages the critical section  
}  
```  
  
 Weitere Informationen dazu, wie Sie kritische Abschnitte mithilfe von `Lock` und `Unlock` schützen, finden Sie unter [Multithreading: Verwendungsweise der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
 Darüber hinaus müssen Sie sicherstellen, dass alle überschriebenen Methoden \(z. B. `Execute`\) threadsicher sind.  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)