---
title: '&lt;cstdbool&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdbool>
- cstdbool
helpviewer_keywords:
- cstdbool header
ms.assetid: 44ccb8b2-d808-4715-8097-58ba09ab33ed
ms.openlocfilehash: ed780e059a5e456731fd6a4f651639e282016f5e
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341105"
---
# <a name="ltcstdboolgt"></a>&lt;cstdbool&gt;

Schließt den C-Standard Bibliotheks \<Header stdbool. h > ein und fügt die verknüpften `std` Namen zum-Namespace hinzu.

> [!NOTE]
> Da der \<stdbool. h-> Header Makros definiert, bei denen C++es sich um Schlüsselwörter in handelt, kann dies auch keine Auswirkungen haben. Der \<stdbool. h-> Header ist in C++veraltet. Der \<cstdbool-> Header ist in c++ 17 veraltet und wurde im Draft c++ 20-Standard entfernt.

## <a name="requirements"></a>Anforderungen

**Header:** \<cstdbool->

**Namespace:** std

## <a name="remarks"></a>Hinweise

Durch einschließen dieses Headers wird sichergestellt, dass die mit externer Verknüpfung im C-Standard Bibliotheks Header deklarierten `std` Namen im-Namespace deklariert werden.

## <a name="see-also"></a>Siehe auch

[Header Dateireferenz](cpp-standard-library-header-files.md)\
[C++Übersicht über die Standardbibliothek](cpp-standard-library-overview.md)\
[Thread Sicherheit in der C++ Standardbibliothek](thread-safety-in-the-cpp-standard-library.md)
