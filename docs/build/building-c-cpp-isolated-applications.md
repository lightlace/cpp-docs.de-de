---
title: Erstellen von C/C++-Anwendungen isolierten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69de94159ef792aedff35efe81e8bb663d571105
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="building-cc-isolated-applications"></a>Erstellen isolierter C/C++-Anwendungen
Eine isolierte Anwendung hängt Side-by-Side Assemblys und bindet an seiner Abhängigkeiten, die über ein Manifest. Es ist nicht erforderlich, für die Anwendung vollständig isoliert, um ordnungsgemäß auf dem Windows ausgeführt werden müssen. Sie können jedoch von investieren in dem Sie die Anwendung vollständig isoliert, Zeit sparen, wenn Sie Ihre Anwendung in der Zukunft service müssen. Weitere Informationen zu den Vorteilen von dem Sie die Anwendung vollständig isoliert, finden Sie unter [isolierte Anwendungen](http://msdn.microsoft.com/library/aa375190).  
  
 Wenn Sie Ihre systemeigene C/C++-Anwendung mit Visual C++ erstellen, generiert Projektsystem Visual Studio standardmäßig eine Manifestdatei, die Ihre Anwendung Abhängigkeiten von Visual C++-Bibliotheken beschreibt. Wenn dies die einzigen Abhängigkeiten sind muss die Anwendung, und er eine isolierte Anwendung ist, sobald es neu mit Visual Studio erstellt wird. Wenn Ihre Anwendung zur Laufzeit andere Bibliotheken verwendet, müssen Sie möglicherweise als Seite-an-Seite-Assemblys, die die Schritte diesen Bibliotheken rebuild [Erstellen von C/C++-Seite-an-Seite-Assemblys](../build/building-c-cpp-side-by-side-assemblies.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Konzept der isolierten Anwendungen und Seite-an-Seite-Assemblys](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)