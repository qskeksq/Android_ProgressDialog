# ProgressDialog
Api level 26 부터 ProgressDialog를 사용할 수 없기 때문에 ProgressBar를 커스터마이징 해서 사용한다

## ConstraintLayout

```java
container = (ConstraintLayout) view.findViewById(R.id.container);

// 1. ProgressBar 생성
progressBar = new ProgressBar(getActivity(),null, android.R.attr.progressBarStyleLarge);

// 2. ConstraintSet 생성
ConstraintSet set = new ConstraintSet();

// 3. ConstraintLayout 속성 불러오기
set.clone(container);

// 4. layout에 addView
container.addView(progressBar);
        
// 5. 위치 지정(중앙)
set.connect(progressBar.getId(), ConstraintSet.LEFT, ConstraintSet.PARENT_ID, ConstraintSet.LEFT, 0);
set.connect(progressBar.getId(), ConstraintSet.RIGHT, ConstraintSet.PARENT_ID, ConstraintSet.RIGHT, 0);
set.connect(progressBar.getId(), ConstraintSet.TOP, ConstraintSet.PARENT_ID, ConstraintSet.TOP, 0);
set.connect(progressBar.getId(), ConstraintSet.BOTTOM, ConstraintSet.PARENT_ID, ConstraintSet.BOTTOM, 0);

// 6. 크기 지정
set.constrainHeight(progressBar.getId(), 200);
set.constrainWidth(progressBar.getId(), 200);

// 7. layout에 적용
set.applyTo(container);
```


## RelativeLayout

```java
container = (RelativeLayout) view.findViewById(R.id.container);

// 1. ProgressBar 생성
progressBar = new ProgressBar(getActivity(),null, android.R.attr.progressBarStyleLarge);

// 2. ProgressBar params 설정
RelativeLayout.LayoutParams params = new RelativeLayout.LayoutParams(100, 100);
params.addRule(RelativeLayout.CENTER_IN_PARENT);

// 3. addView
container.addView(progressBar, params);
```
