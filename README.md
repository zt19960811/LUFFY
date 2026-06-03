# LUFFY Development Repository

> 🚧 **Development Branch** - This is the main development repository for LUFFY (Learning to Reason Under Off‑Policy Guidance)

## About LUFFY

LUFFY is a reinforcement learning framework that bridges the gap between zero-RL and imitation learning by incorporating off-policy reasoning traces into the training process. This repository contains the core implementation and development work.

## 🔧 Development Status

This repository is under active development. Many features are currently being implemented or need refactoring.

## 🚀 Quick Start

⚠️ **Note**: This development version has incomplete implementations. Many features are marked as TODO and need to be completed before production use.

```bash
# Clone the repository
git clone <repository-url>
cd LUFFY

# Install dependencies
pip install -r luffy/requirements.txt

# Note: Some functionality is incomplete - check TODO list below for details
```

## 📁 Repository Structure

```
LUFFY/
├── luffy/                 # Core framework
│   ├── deepscaler/        # Scaling utilities (⚠️ API integration needed)
│   ├── verl/              # RL training components (⚠️ Some features incomplete)
│   └── ...
├── data/                  # Training data and scripts
├── eval_scripts/          # Evaluation utilities
├── exp_scripts/           # Experiment scripts
└── README.md              # This file
```

## ⚠️ Development Notes

- This is a **development version** with incomplete implementations
- Many functions contain TODO markers indicating pending work
- API integrations (OpenAI, Gemini) are currently placeholder implementations
- FSDP and distributed training features need completion


### 🔴 High Priority TODOs

- **API Integration**: OpenAI and Gemini API implementations need completion
- **Reward System**: Parallel processing and validation for reward computation  
- **FSDP Training**: Model loading and distributed training setup
- **Data Processing**: Batch dimension operations and tensor reshaping

### 📝 Complete TODO List

- [ ] **luffy/deepscaler/utils.py:45** - Add logging for API calls and errors
- [ ] **luffy/deepscaler/utils.py:46** - Support batch processing for multiple prompts
- [ ] **luffy/deepscaler/utils.py:47** - Add timeout configuration for API calls
- [ ] **luffy/deepscaler/utils.py:107** - Implement Vertex AI initialization and authentication
- [ ] **luffy/deepscaler/utils.py:108** - Configure safety settings for content generation
- [ ] **luffy/deepscaler/utils.py:109** - Set up GenerativeModel with proper system instructions
- [ ] **luffy/deepscaler/utils.py:110** - Implement retry logic with exponential backoff
- [ ] **luffy/deepscaler/utils.py:111** - Add comprehensive error handling for API access issues
- [ ] **luffy/deepscaler/utils.py:112** - Handle rate limiting and quota management
- [ ] **luffy/deepscaler/utils.py:113** - Implement response validation and text extraction
- [ ] **luffy/deepscaler/utils.py:114** - Add support for different generation configurations
- [ ] **luffy/test.py:1590** - Add smaller page sizes when https://github.com/Dao-AILab/flash-attention/pull/824 is merged
- [ ] **luffy/verl/examples/split_placement/split_monkey_patch.py:141** - Make a canonical logger that supports various backend
- [ ] **luffy/verl/tests/e2e/check_results.py:21** - This function needs error handling
- [ ] **luffy/verl/tests/model/test_transformer.py:22** - Add more models for test
- [ ] **luffy/verl/tests/model/test_transformer.py:50** - We can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformer.py:111** - We can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:34** - Add more models for test
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:81** - We can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:159** - We can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/ray/test_high_level_scheduling_api.py:25** - Pass *args and **kwargs is bug prone and not very convincing
- [ ] **luffy/verl/tests/ray/test_worker_group_basics.py:43** - Pass *args and **kwargs is bug prone and not very convincing
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:54** - Support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:83** - It seems that manual offload is slowly than FSDP offload
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:123** - 1. support create from random initialized model. 2. Support init with FSDP directly
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:163** - Remove this after we switch to fsdp2
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:199** - (zhangchi.usc1992, shengguangming) fix me. Current, auto_wrap_policy causes HFRollout to hang in Gemma
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:207** - Add transformer policy
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:226** - Add more optimizer args into config
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:252** - Support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:263** - A sharding manager that do nothing?
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:391** - Here, we should return all metrics
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:517** - Support DCP and save sharded checkpoints
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:90** - Add other ways to estimate advantages
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:168** - Support each role have individual ray_worker_group_cls,
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:293** - We have to make sure the batch size is divisible by the dp size
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:599** - Make a canonical logger that supports various backend
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:637** - Add response length
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:63** - We have to make sure the batch size is divisible by the dp size
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:437** - Make a canonical logger that supports various backend
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:592** - Check path
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:628** - From remote not implemented yet
- [ ] **luffy/verl/verl/mix_src/mix_vllm_rollout.py:43** - pending implementation
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_attention.py:380** - Llama does not have dropout in the config??
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_decoder.py:78** - Add sequence parallel operator reduce_scatter here
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_decoder.py:86** - Add sequence parallel operator all_gather here
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_decoder.py:90** - Add sequence parallel operator reduce_scatter here
- [ ] **luffy/verl/verl/models/llama/megatron/modeling_llama_megatron.py:37** - pending implementation
- [ ] **luffy/verl/verl/models/llama/megatron/modeling_llama_megatron.py:330** - For better performance, the sp padding should be removed at each layer. Not sure the performance gap
- [ ] **luffy/verl/verl/models/llama/megatron/modeling_llama_megatron.py:588** - For better performance, the sp padding should be removed at each layer. Not sure the performance gap
- [ ] **luffy/verl/verl/models/registry.py:21** - HF may supported more than listed here, we should add more after testing
- [ ] **luffy/verl/verl/models/transformers/llama.py:88** - These transpose are quite inefficient but Flash Attention requires the layout [batch_size, sequence_length, num_heads, head_dim]. We would need to refactor the KV cache
- [ ] **luffy/verl/verl/protocol.py:114** - Optimize memory usage during tensor reshaping
- [ ] **luffy/verl/verl/protocol.py:115** - Add support for different tensor types and shapes
- [ ] **luffy/verl/verl/protocol.py:136** - Optimize tensor view operations for performance
- [ ] **luffy/verl/verl/protocol.py:137** - Add error handling for invalid batch dimensions
- [ ] **luffy/verl/verl/protocol.py:169** - Add consistency check
- [ ] **luffy/verl/verl/protocol.py:265** - We can actually lift this restriction if needed
- [ ] **luffy/verl/verl/protocol.py:351** - Whether to copy
- [ ] **luffy/verl/verl/single_controller/ray/base.py:439** - Create a class with customizable name
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/arg_utils.py:64** - Delete the unused args
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/arg_utils.py:147** - Support fine-grained seeds (e.g., seed per request).
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:237** - Maybe we can hack the autoregressive logics without only apply post process for better performance
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:241** - We can optimize it by making the dataloader yield List[int] without padding.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm.py:257** - Can be optimzied by rewrite the Sampler._get_logprobs() logits
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm_engine_sp.py:99** - Print more configs in debug mode.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm_engine_sp.py:101** - Currently is hfconfig
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm_engine_sp.py:112** - Maybe we can choose init here or from arguments
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm_engine_sp.py:145** - Check get_lora_tokenizer func
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm_engine_sp.py:586** - Check this input
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/llm_engine_sp.py:661** - We may not need to decode
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/model_loader.py:67** - Latest commit in vllm fix awq for this function and add load_weights
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/model_loader.py:96** - Pad to be divided by 4
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/model_loader.py:224** - Change the get_logits part to a separate stage.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/tokenizer.py:56** - The lora tokenizer is also passed, but may be different
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/weight_loaders.py:62** - Check megatron
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/weight_loaders.py:84** - Need to implement a general way to deal with prefix
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/worker.py:109** - Do not use cupy
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/worker.py:209** - Profile swapping overhead and optimize if needed.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_3_1/worker.py:291** - Maybe we should also flag the megatron is initialized
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/arg_utils.py:44** - Served_model_name: Optional[Union[str, List[str]]] = None
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/arg_utils.py:109** - Delete the unused args
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/arg_utils.py:192** - Support fine-grained seeds (e.g., seed per request).
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/arg_utils.py:257** - Spec config
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/config.py:136** - For multimodal model
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/hf_weight_loader.py:81** - With set_default_torch_dtype(next(vllm_model.parameters()).dtype):
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/llm.py:268** - Maybe we can hack the autoregressive logics without only apply post process for better performance
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/llm.py:272** - We can optimize it by making the dataloader yield List[int] without padding.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/llm.py:288** - Can be optimzied by rewrite the Sampler._get_logprobs() logits
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/llm_engine_sp.py:128** - Print more configs in debug mode.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/llm_engine_sp.py:130** - Currently is hfconfig
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/llm_engine_sp.py:143** - Maybe we can choose init here or from arguments
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/llm_engine_sp.py:145** - Check tokenizer class
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/llm_engine_sp.py:153** - Don't know what's the usage
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/llm_engine_sp.py:228** - Add for verl but we may not tokenizer in Rollout
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/llm_engine_sp.py:237** - Check whether we should rebuild the CUDAGraph every iter when offload/load KVCache
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/megatron_weight_loaders.py:67** - Check megatron
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/megatron_weight_loaders.py:254** - Need to implement a general way to deal with prefix
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/megatron_weight_loaders.py:272** - Latest commit in vllm fix awq for this function and add load_weights
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/megatron_weight_loaders.py:325** - Pad to be divided by 4
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/megatron_weight_loaders.py:337** - Remove dependencies from megatron
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/model_loader.py:141** - This is a hack, we need to register the load_weight() func for each model in vllm
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/model_loader.py:226** - This is a hack, we need to register the load_weight() func for each model in vllm
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/model_runner.py:274** - Perform sampling on rank 0
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/parallel_state.py:236** - This will hang
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/parallel_state.py:245** - Will hang when used with device mesh
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/parallel_state.py:247** - Init using device mesh
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/spmd_gpu_executor.py:62** - Verl not support speculative decode now
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/spmd_gpu_executor.py:208** - Not implemented async executor yet
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/tokenizer.py:61** - The lora tokenizer is also passed, but may be different
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/worker.py:30** - Check why vllm has similar file in vllm.model_executor.parallel_utils.parallel_state
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_4_2/worker.py:270** - Check whether need this
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/arg_utils.py:53** - Check this
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/arg_utils.py:54** - Check this
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/arg_utils.py:143** - Delete the unused args
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/arg_utils.py:226** - Support fine-grained seeds (e.g., seed per request).
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/arg_utils.py:366** - Spec config
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/config.py:191** - Check whether this is necessary
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/hf_weight_loader.py:32** - With set_default_torch_dtype(next(vllm_model.parameters()).dtype):
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/llm.py:148** - Check usagecontext
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/llm.py:205** - We can optimize it by making the dataloader yield List[int] without padding.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/llm.py:221** - Can be optimzied by rewrite the Sampler._get_logprobs() logits
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/llm_engine_sp.py:143** - Print more configs in debug mode.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/llm_engine_sp.py:160** - Maybe we can choose init here or from arguments
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/llm_engine_sp.py:262** - Add for verl but we may not tokenizer in Rollout
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/llm_engine_sp.py:271** - Check whether we should rebuild the CUDAGraph every iter when offload/load KVCache
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/megatron_weight_loaders.py:67** - Check megatron
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/megatron_weight_loaders.py:254** - Need to implement a general way to deal with prefix
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/megatron_weight_loaders.py:272** - Latest commit in vllm fix awq for this function and add load_weights
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/model_loader.py:152** - This is a hack, we need to register the load_weight() func for each model in vllm
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/model_loader.py:239** - This is a hack, we need to register the load_weight() func for each model in vllm
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/parallel_state.py:94** - Deviate from the v0.5.4, not pp now
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/parallel_state.py:138** - Check why True is not work in Ray trainer
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/parallel_state.py:165** - Check why True is not work in Ray trainer
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/parallel_state.py:177** - Init using device mesh (not support hybrid engine now)
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/parallel_state.py:249** - Check why True is not work in Ray trainer
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/parallel_state.py:253** - Init using device mesh (not support hybrid engine now)
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/spmd_gpu_executor.py:65** - Verl not support speculative decode now
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/spmd_gpu_executor.py:243** - Not implemented async executor yet
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/tokenizer.py:61** - The lora tokenizer is also passed, but may be different
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/worker.py:29** - Check why vllm has similar file in vllm.model_executor.parallel_utils.parallel_state
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/worker.py:84** - We don't need driver
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/worker.py:103** - Set correct model runner class
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_5_4/worker.py:301** - Check whether need this
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/hf_weight_loader.py:29** - With set_default_torch_dtype(next(vllm_model.parameters()).dtype):
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/llm.py:147** - Check usagecontext
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/llm.py:170** - We can optimize it by making the dataloader yield List[int] without padding.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/llm.py:186** - Can be optimzied by rewrite the Sampler._get_logprobs() logits
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/llm_engine_sp.py:174** - Print more configs in debug mode.
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/llm_engine_sp.py:336** - Add for verl but we may not tokenizer in Rollout
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/llm_engine_sp.py:345** - Check whether we should rebuild the CUDAGraph every iter when offload/load KVCache
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/megatron_weight_loaders.py:68** - Check megatron
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/megatron_weight_loaders.py:255** - Need to implement a general way to deal with prefix
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/megatron_weight_loaders.py:273** - Latest commit in vllm fix awq for this function and add load_weights
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/model_loader.py:170** - This is a hack, we need to register the load_weight() func for each model in vllm
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/model_loader.py:273** - This is a hack, we need to register the load_weight() func for each model in vllm
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/parallel_state.py:97** - Deviate from the v0.5.4, not pp now
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/parallel_state.py:144** - Check why True is not work in Ray trainer
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/parallel_state.py:172** - Check why True is not work in Ray trainer
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/parallel_state.py:185** - Init using device mesh (not support hybrid engine now)
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/parallel_state.py:257** - Check why True is not work in Ray trainer
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/parallel_state.py:262** - Init using device mesh (not support hybrid engine now)
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/spmd_gpu_executor.py:73** - Verl not support speculative decode now
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/spmd_gpu_executor.py:246** - Not implemented async executor yet
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/worker.py:33** - Check why vllm has similar file in vllm.model_executor.parallel_utils.parallel_state
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/worker.py:92** - We don't need driver
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/worker.py:110** - Set correct model runner class
- [ ] **luffy/verl/verl/third_party/vllm/vllm_v_0_6_3/worker.py:311** - Check whether need this
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:16** - pending implementation
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:77** - Add checkpoint manager
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:140** - pending implementation
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:159** - Implement model loading with proper initialization context
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:160** - Add support for different model types and configurations
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:161** - Implement memory-efficient model loading for large models
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:162** - Add model validation and compatibility checks
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:165** - Complete model loading implementation
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:166** - Add support for custom model architectures
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:167** - Implement proper dtype and attention configuration
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:170** - Implement gradient checkpointing configuration
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:171** - Add memory usage optimization strategies
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:172** - Configure mixed precision training settings
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:173** - Implement FSDP sharding and wrapping policies
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:174** - Add CPU offloading configuration for memory optimization
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:175** - Set up distributed training parameters properly
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:178** - Initialize FSDP wrapped model
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:301** - Add a unified tracking
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:318** - Add back checkpoint manager. Currently, it blocks when uploading to hdfs. So very slow.
- [ ] **luffy/verl/verl/trainer/main_ppo.py:50** - Implement reward computation for different data sources
- [ ] **luffy/verl/verl/trainer/main_ppo.py:53** - Add support for parallel processing of reward computation
- [ ] **luffy/verl/verl/trainer/main_ppo.py:54** - Implement proper sequence decoding and validation
- [ ] **luffy/verl/verl/trainer/main_ppo.py:55** - Add thread-safe logging and debugging functionality
- [ ] **luffy/verl/verl/trainer/main_ppo.py:56** - Optimize memory usage for large batch processing
- [ ] **luffy/verl/verl/trainer/main_ppo.py:62** - Extract and validate prompt and response sequences
- [ ] **luffy/verl/verl/trainer/main_ppo.py:63** - Decode sequences to text format
- [ ] **luffy/verl/verl/trainer/main_ppo.py:64** - Apply appropriate reward function based on data source
- [ ] **luffy/verl/verl/trainer/main_ppo.py:65** - Handle edge cases and error conditions
- [ ] **luffy/verl/verl/trainer/main_ppo.py:70** - Implement batch-wise reward computation
- [ ] **luffy/verl/verl/trainer/main_ppo.py:71** - Add proper error handling and validation
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:129** - Add other ways to estimate advantages
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:207** - Add response length
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:330** - Support each role have individual ray_worker_group_cls,
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:379** - We have to make sure the batch size is divisible by the dp size
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:632** - Check path
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:667** - From remote not implemented yet
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:880** - Make a canonical logger that supports various backend
- [ ] **luffy/verl/verl/utils/checkpoint/fsdp_checkpoint_manager.py:101** - Shall we remove previous ckpt every save?
- [ ] **luffy/verl/verl/utils/checkpoint/fsdp_checkpoint_manager.py:135** - Address optimizer is None
- [ ] **luffy/verl/verl/utils/hdfs_io.py:67** - pending implementation
- [ ] **luffy/verl/verl/utils/hdfs_io.py:102** - pending implementation
- [ ] **luffy/verl/verl/utils/megatron/tensor_parallel.py:137** - We may change the implementation later
- [ ] **luffy/verl/verl/utils/megatron_utils.py:202** - Check how to disable megatron timers
- [ ] **luffy/verl/verl/utils/model.py:164** - We can make this faster
- [ ] **luffy/verl/verl/utils/model.py:272** - To find a better way to load mistral7b-rm lm_head
- [ ] **luffy/verl/verl/utils/torch_functional.py:162** - Optimize this. Technically, we only need one broadcast
- [ ] **luffy/verl/verl/utils/torch_functional.py:171** - Optimize this.
- [ ] **luffy/verl/verl/utils/torch_functional.py:362** - Add them back
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:158** - Actually, this function should only return log_prob and this logic should be handled by user outside
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:225** - Actually, we just need to control the sampling order.
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:301** - We may use the new schedule instead
- [ ] **luffy/verl/verl/workers/critic/megatron_critic.py:176** - We may use the new schedule instead
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:88** - Support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:117** - It seems that manual offload is slowly than FSDP offload
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:157** - 1. support create from random initialized model. 2. Support init with FSDP directly
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:197** - Remove this after we switch to fsdp2
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:225** - (zhangchi.usc1992, shengguangming) fix me. Current, auto_wrap_policy causes HFRollout to hang in Gemma
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:233** - Add transformer policy
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:252** - Add more optimizer args into config
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:278** - Support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:289** - A sharding manager that do nothing?
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:416** - Here, we should return all metrics
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:811** - We may need to extract it to dp_reward_model.py
- [ ] **luffy/verl/verl/workers/megatron_workers.py:106** - Currently, we only support reference model param offload
- [ ] **luffy/verl/verl/workers/megatron_workers.py:204** - Add more optimizer args into config
- [ ] **luffy/verl/verl/workers/megatron_workers.py:338** - Here, we should return all metrics
- [ ] **luffy/verl/verl/workers/megatron_workers.py:444** - Support critic model offload
- [ ] **luffy/verl/verl/workers/megatron_workers.py:478** - Support vpp here
- [ ] **luffy/verl/verl/workers/megatron_workers.py:507** - Add more optimizer args into config
- [ ] **luffy/verl/verl/workers/megatron_workers.py:667** - Add more optimizer args into config
- [ ] **luffy/verl/verl/workers/megatron_workers.py:720** - Reward model use itself tokenizer instead of sft tokenizer
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:145** - Check why is bfloat16
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:192** - Actually, we just need to control the sampling order.
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:233** - We may use the new schedule instead
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:16** - Refactor this class. Currently, it will hang when using FSDP HybridShard. We should actually create a single GPU model.
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:98** - Filter out the seq with no answers like ds-chat
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout/vllm_rollout.py:43** - pending implementation
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_ulysses.py:49** - Check how to set seed for each model
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_ulysses.py:56** - Check how to set seed for each model
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:82** - Offload FSDP model weights
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:113** - Current impl doesn't consider FSDP with torch micro-dp
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:122** - Current impl doesn't consider FSDP with torch micro-dp
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:130** - Shall we build a micro_dp group for vllm when integrating with vLLM?
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:76** - After binding to the memory buffer, we can load the checkpoint here
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:253** - This may not be true for FSDP -> vLLM
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:273** - Currently, the implementation is adhoc. We can move this function to the model
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:323** - We can consider copy non-tp weight to another infer buffer.

## 🤝 Contributing

1. Pick a TODO item from the list above
2. Implement the functionality
3. Test your implementation
4. Update this README when TODOs are completed

