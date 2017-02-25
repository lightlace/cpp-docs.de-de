---
title: "Linkertoolwarnung LNK4221 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4221"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4221"
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Linkertoolwarnung LNK4221
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit dieser Objektdatei werden keine zuvor nicht definierten öffentlichen Symbole definiert, weshalb sie von keinem Linkvorgang verwendet wird, der diese Bibliothek nutzt.  
  
 Berücksichtigen Sie die folgenden zwei Codeausschnitte.  
  
```  
// a.cpp  
#include <atlbase.h>  
```  
  
```  
// b.cpp  
#include <atlbase.h>  
int function()  
{  
   return 0;  
}  
  
```  
  
 Um die Dateien zu kompilieren und zwei Objektdateien zu erstellen, führen Sie **cl \/c a.cpp b.cpp** an einer Eingabeaufforderung aus.  Wenn Sie die Objektdateien verknüpfen, indem Sie **link \/lib \/out:test.lib a.obj b.obj** ausführen, empfangen Sie die LNK4221\-Warnung.  Wenn Sie die Objekte verknüpfen, indem Sie **link \/lib \/out:test.lib b.obj a.obj** ausführen, empfangen Sie keine Warnung.  
  
 Im zweiten Szenario wird keine Warnung ausgegeben, da der Linker gemäß der Last\-In First Out \(LIFO\)\-Methode ausgeführt wird.  Im ersten Szenario wird "b.obj" vor "a.obj" verarbeitet, und "a.obj" enthält keine hinzuzufügenden neuen Symbole.  Sie können die Warnung vermeiden, indem Sie den Linker anweisen, zuerst "a.obj" zu verarbeiten.  
  
 Häufig wird dieser Fehler dadurch verursacht, wenn die Option [\/Yc \(Datei der vorkompilierten Header erstellen\)](../../build/reference/yc-create-precompiled-header-file.md) durch zwei Quelldateien mit dem Headerdateinamen angegeben wird, der auch im Feld **Vorkompilierter Header** angegeben wurde.  Eine häufige Ursache dieses Problems hängt mit "stdafx.h" zusammen, da "stdafx.cpp" standardmäßig "stdafx.h" umfasst und keine neue Symbole hinzugefügt werden.  Wenn eine andere Quelldatei "stdafx.h" mit **\/Yc** einschließt und die zugeordnete OBJ\-Datei vor "stdafx.obj" verarbeitet wird, löst der Linker LNK4221 aus.  
  
 Dieses Problem kann u.a dadurch behoben werden, dass für jeden vorkompilierten Header nur eine Quelldatei vorhanden ist, die diesen ihn **\/Yc** einschließt.  Für alle anderen Quelldateien müssen vorkompilierte Header verwendet werden.  Weitere Informationen über das Ändern dieser Einstellung finden Sie unter [\/Yu \(Vorkompilierte Headerdatei verwenden\)](../../build/reference/yu-use-precompiled-header-file.md).