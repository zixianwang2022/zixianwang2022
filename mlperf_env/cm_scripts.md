```

cm run script --tags=run-mlperf,inference,_r4.1-dev,_short,_scc24-base    --model=sdxl      --framework=pytorch    --category=datacenter    --scenario=Offline    --execution_mode=test    --device=rocm    --quiet --precision=float16




# Remove inference cache
cm rm cache --tags=inference,src -f
cm rm cache --tags=inference -f
cm rm cache --tags=python -f
cm pull repo


# Official Implementation
# Performance Estimation for Offline Scenario
cm run script --tags=run-mlperf,inference,_find-performance,_r4.1-dev,_short \
  --model=sdxl \
  --implementation=reference \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm  \
  --quiet \
   --precision=float16




# Formal run
# Official Implementation
cm run script --tags=run-mlperf,inference,_r4.1-dev,_short,_scc24-base \
  --model=sdxl \
  --implementation=reference \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16    --env.CM_GET_PLATFORM_DETAILS=no






# Custom Implementation
# Performance Estimation for Offline Scenario
cm run script --tags=run-mlperf,inference,_find-performance,_r4.1-dev,_short,_scc24-base \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm  \
  --quiet \
   --precision=float16 \
   --adr.mlperf-implementation.tags=_branch.test,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom






# Custom Implementation
# Formal run
cm run script --tags=run-mlperf,inference,_r4.1-dev,_short,_scc24-base \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.test,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no
 


!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
  --rerun # to RERUN the script !!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!


cm run script --tags=run-mlperf,inference,_r4.1-dev,_short,_scc24-base \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.yalu,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no
 





# Full run:
# MGX Implementation
cm run script --tags=run-mlperf,inference,_r4.1-dev,_scc24-main \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.yalu,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no
 
# PyTorch Implementation
cm run script --tags=run-mlperf,inference,_r4.1-dev,_scc24-main \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.test,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no
cm run script --tags=run-mlperf,inference,_r4.1-dev,_scc24-main \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.test,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no \
  --CM_MLPERF_LOADGEN_MAX_BATCHSIZE=2


# PyTorch & Multi-node Implementation
cm run script --tags=run-mlperf,inference,_r4.1-dev,_scc24-main \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.multinode,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no

cm run script --tags=run-mlperf,inference,_r4.1-dev,_scc24-main \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.multinode-test,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no

cm run script --tags=run-mlperf,inference,_r4.1-dev,_scc24-main \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.multinode-test2,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no

```


# Estimate qps performance
```
cm run script --tags=run-mlperf,inference,_find-performance,_r4.1-dev,_short \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.multinode-test2,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no


cm run script --tags=run-mlperf,inference,_r4.1-dev,_scc24-main,_find-performance \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.multinode-test2,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no


```


# Generate actual submission tree
```
cm run script --tags=generate,inference,submission \
  --clean \
  --run-checker \
  --tar=yes \
  --env.CM_TAR_OUTFILE=submission.tar.gz \
  --division=open \
  --category=datacenter \
  --env.CM_DETERMINE_MEMORY_CONFIGURATION=yes \
  --run_style=test \
  --adr.submission-checker.tags=_short-run \
  --quiet \
  --submitter=UCSD




cm run script --tags=push,github,mlperf,inference,submission \
  --repo_url=https://github.com/zixianwang2022/cm4mlperf-inference \
  --repo_branch=mlperf-inference-results-scc24 \
  --commit_message="Results on system MI210" \
  --quiet

```









cm run script --tags=run-mlperf,inference,_r4.1-dev,_scc24-main \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.yalu,_repo.https://github.com/zixianwang2022/mlperf-scc24 --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no
 
```


Test for forked-repo
```
# PyTorch Implementation
```
cm run script --tags=run-mlperf,inference,_r4.1-dev,_scc24-main \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.multigpu-torch-4-pr,_repo.https://github.com/zixianwang2022/inference_4_pr --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no

```


# MIGraphX Implementation
```
cm run script --tags=run-mlperf,inference,_r4.1-dev,_scc24-main \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.multigpu-mgx-4-pr,_repo.https://github.com/zixianwang2022/inference_4_pr --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no \
  --test_query_count=100
```

# PyTorch Multi-node Implementation
```
cm run script --tags=run-mlperf,inference,_r4.1-dev,_scc24-main \
  --model=sdxl \
  --framework=pytorch \
  --category=datacenter \
  --scenario=Offline \
  --execution_mode=test \
  --device=rocm \
  --quiet --precision=float16 \
  --adr.mlperf-implementation.tags=_branch.multi-node-torch-4-pr,_repo.https://github.com/zixianwang2022/inference_4_pr --adr.mlperf-implementation.version=custom  --env.CM_GET_PLATFORM_DETAILS=no \
   --target_qps=1.8

```
