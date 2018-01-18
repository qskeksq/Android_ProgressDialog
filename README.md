# ProgressDialog
Custom ProgressDialog(API 26 ProgressDialog Deprecated)


```java
mapListContainer = (ConstraintLayout) view.findViewById(R.id.mapListContainer);

// 1. ProgressBar 생성
progressBar = new ProgressBar(getActivity(),null, android.R.attr.progressBarStyleLarge);

// 2. ConstraintSet 생성
ConstraintSet set = new ConstraintSet();

// 3. ConstraintLayout 속성 불러오기
set.clone(mapListContainer);

// 4. layout에 addView
mapListContainer.addView(progressBar);
        
// 5. 위치 지정(중앙)
set.connect(progressBar.getId(), ConstraintSet.LEFT, ConstraintSet.PARENT_ID, ConstraintSet.LEFT, 0);
set.connect(progressBar.getId(), ConstraintSet.RIGHT, ConstraintSet.PARENT_ID, ConstraintSet.RIGHT, 0);
set.connect(progressBar.getId(), ConstraintSet.TOP, ConstraintSet.PARENT_ID, ConstraintSet.TOP, 0);
set.connect(progressBar.getId(), ConstraintSet.BOTTOM, ConstraintSet.PARENT_ID, ConstraintSet.BOTTOM, 0);

// 6. 크기 지정
set.constrainHeight(progressBar.getId(), 200);
set.constrainWidth(progressBar.getId(), 200);

// 7. layout에 적용
set.applyTo(mapListContainer);
```
