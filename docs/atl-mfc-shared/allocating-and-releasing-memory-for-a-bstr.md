---
title: Zuweisen und Freigeben von Arbeitsspeicher für einen BSTR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- bstr
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46ab5ae9d6f0bfa98231cbc41aa4ae0d10b89537
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358324"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>Zuweisen und Freigeben von Arbeitsspeicher für einen BSTR
Beim Erstellen von `BSTR`s und zwischen COM-Objekte zu übergeben, achten Sie in der zum Behandeln von den Arbeitsspeicher, die sie verwenden, um Speicherverluste zu vermeiden. Wenn eine `BSTR` bleibt in einer Schnittstelle, müssen Sie ihren Arbeitsspeicher freigeben, wenn Sie damit fertig sind. Jedoch, dass bei einem `BSTR` übergibt Out eine Schnittstelle, das empfangende Objekt übernimmt die Verantwortung für die Verwaltung des Arbeitsspeichers.  
  
 Im Allgemeinen die Regeln für das zuordnen und Freigeben von Arbeitsspeicher für zugewiesene `BSTR`s lauten wie folgt:  
  
-   Wenn Sie einen Aufruf an eine Funktion, erwartet eine `BSTR` Argument, müssen Sie den Speicher für Reservieren der `BSTR` vor dem Aufruf und geben Sie es anschließend. Zum Beispiel:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]  
  
-   Wenn Sie einen Aufruf an eine Funktion, zurückgibt eine `BSTR`, Sie müssen die Zeichenfolge selbst freigeben. Zum Beispiel:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]  
  
-   Eine Funktion, die Gibt beim Implementieren einer `BSTR`, weisen Sie die Zeichenfolge jedoch nicht freigeben und. Der Empfang die Funktion gibt den Arbeitsspeicher frei. Zum Beispiel:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)   
 [SysAllocString](https://msdn.microsoft.com/library/windows/desktop/ms221458.aspx)   
 [SysFreeString](https://msdn.microsoft.com/library/windows/desktop/ms221481.aspx)

