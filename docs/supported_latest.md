# Zeitgeist 20.45.x

## System

| Name                    | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                         |
| ----------------------- | ------ | --------- | --------- | ------- | --------------------------------- |
| Fill block              |        |           |           |         | `Perbill`ratio<br/>               |
| Remark                  |        |           |           |         | `Bytes`remark<br/>                |
| Set heap pages          |        |           |           |         | `u64`pages<br/>                   |
| Set code                |        |           |           |         | `Vecu8`code<br/>                  |
| Set code without checks |        |           |           |         | `Vecu8`code<br/>                  |
| Set storage             |        |           |           |         | `VecKeyValue`items<br/>           |
| Kill storage            |        |           |           |         | `VecKey`keys<br/>                 |
| Kill prefix             |        |           |           |         | `Key`prefix<br/>`u32`subkeys<br/> |
| Remark with event       |        |           |           |         | `Bytes`remark<br/>                |

## Timestamp

| Name | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments            |
| ---- | ------ | --------- | --------- | ------- | -------------------- |
| Set  |        |           |           |         | `Compactu64`now<br/> |

## Scheduler

| Name                 | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                                           |
| -------------------- | ------ | --------- | --------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Schedule             |        |           |           |         | `BlockNumber`when<br/>`OptionschedulePeriodBlockNumber`maybe_periodic<br/>`schedulePriority`priority<br/>`BoxCallOrHashOfT`call<br/>                |
| Cancel               |        |           |           |         | `BlockNumber`when<br/>`u32`index<br/>                                                                                                               |
| Schedule named       |        |           |           |         | `Vecu8`id<br/>`BlockNumber`when<br/>`OptionschedulePeriodBlockNumber`maybe_periodic<br/>`schedulePriority`priority<br/>`BoxCallOrHashOfT`call<br/>  |
| Cancel named         |        |           |           |         | `Vecu8`id<br/>                                                                                                                                      |
| Schedule after       |        |           |           |         | `BlockNumber`after<br/>`OptionschedulePeriodBlockNumber`maybe_periodic<br/>`schedulePriority`priority<br/>`BoxCallOrHashOfT`call<br/>               |
| Schedule named after |        |           |           |         | `Vecu8`id<br/>`BlockNumber`after<br/>`OptionschedulePeriodBlockNumber`maybe_periodic<br/>`schedulePriority`priority<br/>`BoxCallOrHashOfT`call<br/> |

## Preimage

| Name               | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments         |
| ------------------ | ------ | --------- | --------- | ------- | ----------------- |
| Note preimage      |        |           |           |         | `Vecu8`bytes<br/> |
| Unnote preimage    |        |           |           |         | `Hash`hash<br/>   |
| Request preimage   |        |           |           |         | `Hash`hash<br/>   |
| Unrequest preimage |        |           |           |         | `Hash`hash<br/>   |

## Balances

| Name                | Nano S             | Nano S XL          | Nano SP/X          | Nesting            | Arguments                                                                                  |
| ------------------- | ------------------ | ------------------ | ------------------ | ------------------ | ------------------------------------------------------------------------------------------ |
| Transfer            | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | `AccountIdLookupOfT`dest<br/>`CompactBalance`amount<br/>                                   |
| Set balance         |                    | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | `AccountIdLookupOfT`who<br/>`CompactBalance`new_free<br/>`CompactBalance`new_reserved<br/> |
| Force transfer      | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | `AccountIdLookupOfT`source<br/>`AccountIdLookupOfT`dest<br/>`CompactBalance`amount<br/>    |
| Transfer keep alive | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | `AccountIdLookupOfT`dest<br/>`CompactBalance`amount<br/>                                   |
| Transfer all        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |                    | `AccountIdLookupOfT`dest<br/>`bool`keep_alive<br/>                                         |
| Force unreserve     |                    | :heavy_check_mark: | :heavy_check_mark: |                    | `AccountIdLookupOfT`who<br/>`Balance`amount<br/>                                           |

## Treasury

| Name             | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                       |
| ---------------- | ------ | --------- | --------- | ------- | --------------------------------------------------------------- |
| Propose spend    |        |           |           |         | `CompactBalance`amount<br/>`AccountIdLookupOfT`beneficiary<br/> |
| Reject proposal  |        |           |           |         | `Compactu32`proposal_id<br/>                                    |
| Approve proposal |        |           |           |         | `Compactu32`proposal_id<br/>                                    |
| Spend            |        |           |           |         | `CompactBalance`amount<br/>`AccountIdLookupOfT`beneficiary<br/> |
| Remove approval  |        |           |           |         | `Compactu32`proposal_id<br/>                                    |

## Vesting

| Name                  | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                |
| --------------------- | ------ | --------- | --------- | ------- | ---------------------------------------------------------------------------------------- |
| Vest                  |        |           |           |         |                                                                                          |
| Vest other            |        |           |           |         | `AccountIdLookupOfT`target<br/>                                                          |
| Vested transfer       |        |           |           |         | `AccountIdLookupOfT`target<br/>`VestingInfo`schedule<br/>                                |
| Force vested transfer |        |           |           |         | `AccountIdLookupOfT`source<br/>`AccountIdLookupOfT`target<br/>`VestingInfo`schedule<br/> |
| Merge schedules       |        |           |           |         | `u32`schedule1_index<br/>`u32`schedule2_index<br/>                                       |

## MultiSig

| Name                 | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                                                     |
| -------------------- | ------ | --------- | --------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| As multi threshold 1 |        |           |           |         | `VecAccountId`other_signatories<br/>`Call`call<br/>                                                                                                           |
| As multi             |        |           |           |         | `u16`threshold<br/>`VecAccountId`other_signatories<br/>`OptionTimepoint`maybe_timepoint<br/>`OpaqueCall`call<br/>`bool`store_call<br/>`Weight`max_weight<br/> |
| Approve as multi     |        |           |           |         | `u16`threshold<br/>`VecAccountId`other_signatories<br/>`OptionTimepoint`maybe_timepoint<br/>`H256`call_hash<br/>`Weight`max_weight<br/>                       |
| Cancel as multi      |        |           |           |         | `u16`threshold<br/>`VecAccountId`other_signatories<br/>`Timepoint`timepoint<br/>`H256`call_hash<br/>                                                          |

## Bounties

| Name                 | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                          |
| -------------------- | ------ | --------- | --------- | ------- | ---------------------------------------------------------------------------------- |
| Propose bounty       |        |           |           |         | `CompactBalance`amount<br/>`Bytes`description<br/>                                 |
| Approve bounty       |        |           |           |         | `Compactu32`bounty_id<br/>                                                         |
| Propose curator      |        |           |           |         | `Compactu32`bounty_id<br/>`AccountIdLookupOfT`curator<br/>`CompactBalance`fee<br/> |
| Unassign curator     |        |           |           |         | `Compactu32`bounty_id<br/>                                                         |
| Accept curator       |        |           |           |         | `Compactu32`bounty_id<br/>                                                         |
| Award bounty         |        |           |           |         | `Compactu32`bounty_id<br/>`AccountIdLookupOfT`beneficiary<br/>                     |
| Claim bounty         |        |           |           |         | `Compactu32`bounty_id<br/>                                                         |
| Close bounty         |        |           |           |         | `Compactu32`bounty_id<br/>                                                         |
| Extend bounty expiry |        |           |           |         | `Compactu32`bounty_id<br/>`Bytes`remark<br/>                                       |

## Democracy

| Name                               | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                      |
| ---------------------------------- | ------ | --------- | --------- | ------- | ------------------------------------------------------------------------------ |
| Propose                            |        |           |           |         | `Hash`proposal_hash<br/>`CompactBalance`amount<br/>                            |
| Second                             |        |           |           |         | `Compactu32`proposal<br/>`Compactu32`seconds_upper_bound<br/>                  |
| Vote                               |        |           |           |         | `Compactu32`ref_index<br/>`AccountVote`vote<br/>                               |
| Emergency cancel                   |        |           |           |         | `ReferendumIndex`ref_index<br/>                                                |
| External propose                   |        |           |           |         | `Hash`proposal_hash<br/>                                                       |
| External propose majority          |        |           |           |         | `Hash`proposal_hash<br/>                                                       |
| External propose default           |        |           |           |         | `Hash`proposal_hash<br/>                                                       |
| Fast track                         |        |           |           |         | `Hash`proposal_hash<br/>`BlockNumber`voting_period<br/>`BlockNumber`delay<br/> |
| Veto external                      |        |           |           |         | `Hash`proposal_hash<br/>                                                       |
| Cancel referendum                  |        |           |           |         | `Compactu32`ref_index<br/>                                                     |
| Cancel queued                      |        |           |           |         | `ReferendumIndex`which<br/>                                                    |
| Delegate                           |        |           |           |         | `AccountIdLookupOfT`to<br/>`Conviction`conviction<br/>`Balance`balance<br/>    |
| Undelegate                         |        |           |           |         |                                                                                |
| Clear public proposals             |        |           |           |         |                                                                                |
| Note preimage                      |        |           |           |         | `Bytes`encoded_proposal<br/>                                                   |
| Note preimage operational          |        |           |           |         | `Bytes`encoded_proposal<br/>                                                   |
| Note imminent preimage             |        |           |           |         | `Bytes`encoded_proposal<br/>                                                   |
| Note imminent preimage operational |        |           |           |         | `Bytes`encoded_proposal<br/>                                                   |
| Reap preimage                      |        |           |           |         | `Hash`proposal_hash<br/>`Compactu32`proposal_len_upper_bound<br/>              |
| Unlock                             |        |           |           |         | `AccountIdLookupOfT`target<br/>                                                |
| Remove vote                        |        |           |           |         | `ReferendumIndex`index<br/>                                                    |
| Remove other vote                  |        |           |           |         | `AccountIdLookupOfT`target<br/>`ReferendumIndex`index<br/>                     |
| Enact proposal                     |        |           |           |         | `Hash`proposal_hash<br/>`ReferendumIndex`index<br/>                            |
| Blacklist                          |        |           |           |         | `Hash`proposal_hash<br/>`OptionReferendumIndex`maybe_ref_index<br/>            |
| Cancel proposal                    |        |           |           |         | `Compactu32`prop_index<br/>                                                    |

## AdvisoryCommittee

| Name                | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                         |
| ------------------- | ------ | --------- | --------- | ------- | ----------------------------------------------------------------------------------------------------------------- |
| Set members         |        |           |           |         | `VecAccountId`new_members<br/>`OptionAccountId`prime<br/>`MemberCount`old_count<br/>                              |
| Execute             |        |           |           |         | `Proposal`proposal<br/>`Compactu32`length_bound<br/>                                                              |
| Propose             |        |           |           |         | `Compactu32`threshold<br/>`Proposal`proposal<br/>`Compactu32`length_bound<br/>                                    |
| Vote                |        |           |           |         | `Hash`proposal<br/>`Compactu32`index<br/>`bool`approve<br/>                                                       |
| Close               |        |           |           |         | `Hash`proposal_hash<br/>`Compactu32`index<br/>`Compactu64`proposal_weight_bound<br/>`Compactu32`length_bound<br/> |
| Disapprove proposal |        |           |           |         | `Hash`proposal_hash<br/>                                                                                          |

## AdvisoryCommitteeMembership

| Name          | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                   |
| ------------- | ------ | --------- | --------- | ------- | ----------------------------------------------------------- |
| Add member    |        |           |           |         | `AccountIdLookupOfT`who<br/>                                |
| Remove member |        |           |           |         | `AccountIdLookupOfT`who<br/>                                |
| Swap member   |        |           |           |         | `AccountIdLookupOfT`remove<br/>`AccountIdLookupOfT`add<br/> |
| Reset members |        |           |           |         | `VecAccountId`members<br/>                                  |
| Change key    |        |           |           |         | `AccountIdLookupOfT`new\_<br/>                              |
| Set prime     |        |           |           |         | `AccountIdLookupOfT`who<br/>                                |
| Clear prime   |        |           |           |         |                                                             |

## Council

| Name                | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                         |
| ------------------- | ------ | --------- | --------- | ------- | ----------------------------------------------------------------------------------------------------------------- |
| Set members         |        |           |           |         | `VecAccountId`new_members<br/>`OptionAccountId`prime<br/>`MemberCount`old_count<br/>                              |
| Execute             |        |           |           |         | `Proposal`proposal<br/>`Compactu32`length_bound<br/>                                                              |
| Propose             |        |           |           |         | `Compactu32`threshold<br/>`Proposal`proposal<br/>`Compactu32`length_bound<br/>                                    |
| Vote                |        |           |           |         | `Hash`proposal<br/>`Compactu32`index<br/>`bool`approve<br/>                                                       |
| Close               |        |           |           |         | `Hash`proposal_hash<br/>`Compactu32`index<br/>`Compactu64`proposal_weight_bound<br/>`Compactu32`length_bound<br/> |
| Disapprove proposal |        |           |           |         | `Hash`proposal_hash<br/>                                                                                          |

## CouncilMembership

| Name          | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                   |
| ------------- | ------ | --------- | --------- | ------- | ----------------------------------------------------------- |
| Add member    |        |           |           |         | `AccountIdLookupOfT`who<br/>                                |
| Remove member |        |           |           |         | `AccountIdLookupOfT`who<br/>                                |
| Swap member   |        |           |           |         | `AccountIdLookupOfT`remove<br/>`AccountIdLookupOfT`add<br/> |
| Reset members |        |           |           |         | `VecAccountId`members<br/>                                  |
| Change key    |        |           |           |         | `AccountIdLookupOfT`new\_<br/>                              |
| Set prime     |        |           |           |         | `AccountIdLookupOfT`who<br/>                                |
| Clear prime   |        |           |           |         |                                                             |

## TechnicalCommittee

| Name                | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                         |
| ------------------- | ------ | --------- | --------- | ------- | ----------------------------------------------------------------------------------------------------------------- |
| Set members         |        |           |           |         | `VecAccountId`new_members<br/>`OptionAccountId`prime<br/>`MemberCount`old_count<br/>                              |
| Execute             |        |           |           |         | `Proposal`proposal<br/>`Compactu32`length_bound<br/>                                                              |
| Propose             |        |           |           |         | `Compactu32`threshold<br/>`Proposal`proposal<br/>`Compactu32`length_bound<br/>                                    |
| Vote                |        |           |           |         | `Hash`proposal<br/>`Compactu32`index<br/>`bool`approve<br/>                                                       |
| Close               |        |           |           |         | `Hash`proposal_hash<br/>`Compactu32`index<br/>`Compactu64`proposal_weight_bound<br/>`Compactu32`length_bound<br/> |
| Disapprove proposal |        |           |           |         | `Hash`proposal_hash<br/>                                                                                          |

## TechnicalCommitteeMembership

| Name          | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                   |
| ------------- | ------ | --------- | --------- | ------- | ----------------------------------------------------------- |
| Add member    |        |           |           |         | `AccountIdLookupOfT`who<br/>                                |
| Remove member |        |           |           |         | `AccountIdLookupOfT`who<br/>                                |
| Swap member   |        |           |           |         | `AccountIdLookupOfT`remove<br/>`AccountIdLookupOfT`add<br/> |
| Reset members |        |           |           |         | `VecAccountId`members<br/>                                  |
| Change key    |        |           |           |         | `AccountIdLookupOfT`new\_<br/>                              |
| Set prime     |        |           |           |         | `AccountIdLookupOfT`who<br/>                                |
| Clear prime   |        |           |           |         |                                                             |

## Identity

| Name              | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                       |
| ----------------- | ------ | --------- | --------- | ------- | --------------------------------------------------------------------------------------------------------------- |
| Add registrar     |        |           |           |         | `AccountIdLookupOfT`account<br/>                                                                                |
| Set identity      |        |           |           |         | `IdentityInfo`info<br/>                                                                                         |
| Set subs          |        |           |           |         | `VecTupleAccountIdData`subs<br/>                                                                                |
| Clear identity    |        |           |           |         |                                                                                                                 |
| Request judgement |        |           |           |         | `Compactu32`reg_index<br/>`Compactu128`max_fee<br/>                                                             |
| Cancel request    |        |           |           |         | `RegistrarIndex`reg_index<br/>                                                                                  |
| Set fee           |        |           |           |         | `Compactu32`index<br/>`Compactu128`fee<br/>                                                                     |
| Set account id    |        |           |           |         | `Compactu32`index<br/>`AccountIdLookupOfT`new\_<br/>                                                            |
| Set fields        |        |           |           |         | `Compactu32`index<br/>`IdentityFields`fields<br/>                                                               |
| Provide judgement |        |           |           |         | `Compactu32`reg_index<br/>`AccountIdLookupOfT`target<br/>`JudgementBalanceOfT`judgement<br/>`Hash`identity<br/> |
| Kill identity     |        |           |           |         | `AccountIdLookupOfT`target<br/>                                                                                 |
| Add sub           |        |           |           |         | `AccountIdLookupOfT`sub<br/>`Data`data<br/>                                                                     |
| Rename sub        |        |           |           |         | `AccountIdLookupOfT`sub<br/>`Data`data<br/>                                                                     |
| Remove sub        |        |           |           |         | `AccountIdLookupOfT`sub<br/>                                                                                    |
| Quit sub          |        |           |           |         |                                                                                                                 |

## Utility

| Name          | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                       |
| ------------- | ------ | --------- | --------- | ------- | ----------------------------------------------- |
| Batch         |        |           |           |         | `VecCall`calls<br/>                             |
| As derivative |        |           |           |         | `u16`index<br/>`Call`call<br/>                  |
| Batch all     |        |           |           |         | `VecCall`calls<br/>                             |
| Dispatch as   |        |           |           |         | `BoxPalletsOrigin`as_origin<br/>`Call`call<br/> |
| Force batch   |        |           |           |         | `VecCall`calls<br/>                             |

## Proxy

| Name                | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                  |
| ------------------- | ------ | --------- | --------- | ------- | -------------------------------------------------------------------------------------------------------------------------- |
| Proxy               |        |           |           |         | `AccountIdLookupOfT`real<br/>`OptionProxyType`force_proxy_type<br/>`Call`call<br/>                                         |
| Add proxy           |        |           |           |         | `AccountIdLookupOfT`delegate<br/>`ProxyType`proxy_type<br/>`BlockNumber`delay<br/>                                         |
| Remove proxy        |        |           |           |         | `AccountIdLookupOfT`delegate<br/>`ProxyType`proxy_type<br/>`BlockNumber`delay<br/>                                         |
| Remove proxies      |        |           |           |         |                                                                                                                            |
| Anonymous           |        |           |           |         | `ProxyType`proxy_type<br/>`BlockNumber`delay<br/>`u16`index<br/>                                                           |
| Kill anonymous      |        |           |           |         | `AccountIdLookupOfT`spawner<br/>`ProxyType`proxy_type<br/>`u16`index<br/>`Compactu64`height<br/>`Compactu32`ext_index<br/> |
| Announce            |        |           |           |         | `AccountIdLookupOfT`real<br/>`CallHashOf`call_hash<br/>                                                                    |
| Remove announcement |        |           |           |         | `AccountIdLookupOfT`real<br/>`CallHashOf`call_hash<br/>                                                                    |
| Reject announcement |        |           |           |         | `AccountIdLookupOfT`delegate<br/>`CallHashOf`call_hash<br/>                                                                |
| Proxy announced     |        |           |           |         | `AccountIdLookupOfT`delegate<br/>`AccountIdLookupOfT`real<br/>`OptionProxyType`force_proxy_type<br/>`Call`call<br/>        |

## AssetManager

| Name                     | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                 |
| ------------------------ | ------ | --------- | --------- | ------- | ----------------------------------------------------------------------------------------- |
| Transfer                 |        |           |           |         | `LookupasStaticLookupSource`dest<br/>`CurrencyId`currency_id<br/>`Compactu128`amount<br/> |
| Transfer native currency |        |           |           |         | `LookupasStaticLookupSource`dest<br/>`Compactu128`amount<br/>                             |
| Update balance           |        |           |           |         | `LookupasStaticLookupSource`who<br/>`CurrencyId`currency_id<br/>`Amount`amount<br/>       |

## Authorized

| Name                     | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                              |
| ------------------------ | ------ | --------- | --------- | ------- | ------------------------------------------------------ |
| Authorize market outcome |        |           |           |         | `MarketIdOfT`market_id<br/>`OutcomeReport`outcome<br/> |

## Court

| Name       | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                              |
| ---------- | ------ | --------- | --------- | ------- | ------------------------------------------------------ |
| Exit court |        |           |           |         |                                                        |
| Join court |        |           |           |         |                                                        |
| Vote       |        |           |           |         | `Compactu128`market_id<br/>`OutcomeReport`outcome<br/> |

## LiquidityMining

| Name                       | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                |
| -------------------------- | ------ | --------- | --------- | ------- | ---------------------------------------- |
| Set per block distribution |        |           |           |         | `Compactu128`per_block_distribution<br/> |

## Swaps

| Name                              | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                                                                                      |
| --------------------------------- | ------ | --------- | --------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Admin clean up pool               |        |           |           |         | `Compactu128`market_id<br/>`OutcomeReport`outcome_report<br/>                                                                                                                                  |
| Pool exit                         |        |           |           |         | `Compactu128`pool_id<br/>`Compactu128`pool_amount<br/>`VecBalanceOfT`min_assets_out<br/>                                                                                                       |
| Pool exit subsidy                 |        |           |           |         | `Compactu128`pool_id<br/>`Compactu128`amount<br/>                                                                                                                                              |
| Pool exit with exact asset amount |        |           |           |         | `Compactu128`pool_id<br/>`AssetMarketIdOfT`asset<br/>`Compactu128`asset_amount<br/>`Compactu128`max_pool_amount<br/>                                                                           |
| Pool exit with exact pool amount  |        |           |           |         | `Compactu128`pool_id<br/>`AssetMarketIdOfT`asset<br/>`Compactu128`pool_amount<br/>`Compactu128`min_asset_amount<br/>                                                                           |
| Pool join                         |        |           |           |         | `Compactu128`pool_id<br/>`Compactu128`pool_amount<br/>`VecBalanceOfT`max_assets_in<br/>                                                                                                        |
| Pool join subsidy                 |        |           |           |         | `Compactu128`pool_id<br/>`Compactu128`amount<br/>                                                                                                                                              |
| Pool join with exact asset amount |        |           |           |         | `Compactu128`pool_id<br/>`AssetMarketIdOfT`asset_in<br/>`Compactu128`asset_amount<br/>`Compactu128`min_pool_amount<br/>                                                                        |
| Pool join with exact pool amount  |        |           |           |         | `Compactu128`pool_id<br/>`AssetMarketIdOfT`asset<br/>`Compactu128`pool_amount<br/>`Compactu128`max_asset_amount<br/>                                                                           |
| Swap exact amount in              |        |           |           |         | `Compactu128`pool_id<br/>`AssetMarketIdOfT`asset_in<br/>`Compactu128`asset_amount_in<br/>`AssetMarketIdOfT`asset_out<br/>`OptionBalance`min_asset_amount_out<br/>`OptionBalance`max_price<br/> |
| Swap exact amount out             |        |           |           |         | `Compactu128`pool_id<br/>`AssetMarketIdOfT`asset_in<br/>`OptionBalance`max_asset_amount_in<br/>`AssetMarketIdOfT`asset_out<br/>`Compactu128`asset_amount_out<br/>`OptionBalance`max_price<br/> |

## PredictionMarkets

| Name                                      | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                                                                                                                                                                                                         |
| ----------------------------------------- | ------ | --------- | --------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Admin destroy market                      |        |           |           |         | `Compactu128`market_id<br/>                                                                                                                                                                                                                                                                                       |
| Admin move market to closed               |        |           |           |         | `Compactu128`market_id<br/>                                                                                                                                                                                                                                                                                       |
| Admin move market to resolved             |        |           |           |         | `Compactu128`market_id<br/>                                                                                                                                                                                                                                                                                       |
| Approve market                            |        |           |           |         | `Compactu128`market_id<br/>                                                                                                                                                                                                                                                                                       |
| Request edit                              |        |           |           |         | `Compactu128`market_id<br/>`Vecu8`edit_reason<br/>                                                                                                                                                                                                                                                                |
| Buy complete set                          |        |           |           |         | `Compactu128`market_id<br/>`Compactu128`amount<br/>                                                                                                                                                                                                                                                               |
| Dispute                                   |        |           |           |         | `Compactu128`market_id<br/>`OutcomeReport`outcome<br/>                                                                                                                                                                                                                                                            |
| Create cpmm market and deploy assets      |        |           |           |         | `AssetMarketIdOfT`base_asset<br/>`AccountId`oracle<br/>`MarketPeriodBlockNumberMomentOfT`period<br/>`DeadlinesBlockNumber`deadlines<br/>`MultiHash`metadata<br/>`MarketType`market_type<br/>`MarketDisputeMechanism`dispute_mechanism<br/>`Compactu128`swap_fee<br/>`Compactu128`amount<br/>`Vecu128`weights<br/> |
| Create market                             |        |           |           |         | `AssetMarketIdOfT`base_asset<br/>`AccountId`oracle<br/>`MarketPeriodBlockNumberMomentOfT`period<br/>`DeadlinesBlockNumber`deadlines<br/>`MultiHash`metadata<br/>`MarketCreation`creation<br/>`MarketType`market_type<br/>`MarketDisputeMechanism`dispute_mechanism<br/>`ScoringRule`scoring_rule<br/>             |
| Edit market                               |        |           |           |         | `AssetMarketIdOfT`base_asset<br/>`MarketIdOfT`market_id<br/>`AccountId`oracle<br/>`MarketPeriodBlockNumberMomentOfT`period<br/>`DeadlinesBlockNumber`deadlines<br/>`MultiHash`metadata<br/>`MarketType`market_type<br/>`MarketDisputeMechanism`dispute_mechanism<br/>`ScoringRule`scoring_rule<br/>               |
| Deploy swap pool and additional liquidity |        |           |           |         | `Compactu128`market_id<br/>`Compactu128`swap_fee<br/>`Compactu128`amount<br/>`Vecu128`weights<br/>                                                                                                                                                                                                                |
| Deploy swap pool for market               |        |           |           |         | `Compactu128`market_id<br/>`Compactu128`swap_fee<br/>`Compactu128`amount<br/>`Vecu128`weights<br/>                                                                                                                                                                                                                |
| Redeem shares                             |        |           |           |         | `Compactu128`market_id<br/>                                                                                                                                                                                                                                                                                       |
| Reject market                             |        |           |           |         | `Compactu128`market_id<br/>`Vecu8`reject_reason<br/>                                                                                                                                                                                                                                                              |
| Report                                    |        |           |           |         | `Compactu128`market_id<br/>`OutcomeReport`outcome<br/>                                                                                                                                                                                                                                                            |
| Sell complete set                         |        |           |           |         | `Compactu128`market_id<br/>`Compactu128`amount<br/>                                                                                                                                                                                                                                                               |
| Start global dispute                      |        |           |           |         | `Compactu128`market_id<br/>                                                                                                                                                                                                                                                                                       |

## Styx

| Name            | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                |
| --------------- | ------ | --------- | --------- | ------- | ------------------------ |
| Cross           |        |           |           |         |                          |
| Set burn amount |        |           |           |         | `Compactu128`amount<br/> |

## ParachainSystem

| Name                     | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                        |
| ------------------------ | ------ | --------- | --------- | ------- | -------------------------------- |
| Set validation data      |        |           |           |         | `ParachainInherentData`data<br/> |
| Sudo send upward message |        |           |           |         | `UpwardMessage`message<br/>      |
| Authorize upgrade        |        |           |           |         | `Hash`code_hash<br/>             |
| Enact authorized upgrade |        |           |           |         | `Vecu8`code<br/>                 |

## ParachainStaking

| Name                                                | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                                                                                   |
| --------------------------------------------------- | ------ | --------- | --------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Set staking expectations                            |        |           |           |         | `RangeBalanceOfT`expectations<br/>                                                                                                                                                          |
| Set inflation                                       |        |           |           |         | `RangePerbill`schedule<br/>                                                                                                                                                                 |
| Set parachain bond account                          |        |           |           |         | `AccountId`new\_<br/>                                                                                                                                                                       |
| Set parachain bond reserve percent                  |        |           |           |         | `Percent`new\_<br/>                                                                                                                                                                         |
| Set total selected                                  |        |           |           |         | `u32`new\_<br/>                                                                                                                                                                             |
| Set collator commission                             |        |           |           |         | `Perbill`new\_<br/>                                                                                                                                                                         |
| Set blocks per round                                |        |           |           |         | `u32`new\_<br/>                                                                                                                                                                             |
| Join candidates                                     |        |           |           |         | `Balance`bond<br/>`u32`candidate_count<br/>                                                                                                                                                 |
| Schedule leave candidates                           |        |           |           |         | `u32`candidate_count<br/>                                                                                                                                                                   |
| Execute leave candidates                            |        |           |           |         | `AccountId`candidate<br/>`u32`candidate_delegation_count<br/>                                                                                                                               |
| Cancel leave candidates                             |        |           |           |         | `u32`candidate_count<br/>                                                                                                                                                                   |
| Go offline                                          |        |           |           |         |                                                                                                                                                                                             |
| Go online                                           |        |           |           |         |                                                                                                                                                                                             |
| Candidate bond more                                 |        |           |           |         | `Balance`more<br/>                                                                                                                                                                          |
| Schedule candidate bond less                        |        |           |           |         | `Balance`less<br/>                                                                                                                                                                          |
| Execute candidate bond less                         |        |           |           |         | `AccountId`candidate<br/>                                                                                                                                                                   |
| Cancel candidate bond less                          |        |           |           |         |                                                                                                                                                                                             |
| Delegate                                            |        |           |           |         | `AccountId`candidate<br/>`Balance`amount<br/>`u32`candidate_delegation_count<br/>`u32`delegation_count<br/>                                                                                 |
| Delegate with auto compound                         |        |           |           |         | `AccountId`candidate<br/>`Balance`amount<br/>`Percent`auto_compound<br/>`u32`candidate_delegation_count<br/>`u32`candidate_auto_compounding_delegation_count<br/>`u32`delegation_count<br/> |
| Schedule leave delegators                           |        |           |           |         |                                                                                                                                                                                             |
| Execute leave delegators                            |        |           |           |         | `AccountId`delegator<br/>`u32`delegation_count<br/>                                                                                                                                         |
| Cancel leave delegators                             |        |           |           |         |                                                                                                                                                                                             |
| Schedule revoke delegation                          |        |           |           |         | `AccountId`collator<br/>                                                                                                                                                                    |
| Delegator bond more                                 |        |           |           |         | `AccountId`candidate<br/>`Balance`more<br/>                                                                                                                                                 |
| Schedule delegator bond less                        |        |           |           |         | `AccountId`candidate<br/>`Balance`less<br/>                                                                                                                                                 |
| Execute delegation request                          |        |           |           |         | `AccountId`delegator<br/>`AccountId`candidate<br/>                                                                                                                                          |
| Cancel delegation request                           |        |           |           |         | `AccountId`candidate<br/>                                                                                                                                                                   |
| Set auto compound                                   |        |           |           |         | `AccountId`candidate<br/>`Percent`value<br/>`u32`candidate_auto_compounding_delegation_count_hint<br/>`u32`delegation_count_hint<br/>                                                       |
| Hotfix remove delegation requests exited candidates |        |           |           |         | `VecAccountId`candidates<br/>                                                                                                                                                               |

## AuthorInherent

| Name                           | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments |
| ------------------------------ | ------ | --------- | --------- | ------- | --------- |
| Kick off authorship validation |        |           |           |         |           |

## AuthorFilter

| Name         | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                    |
| ------------ | ------ | --------- | --------- | ------- | ---------------------------- |
| Set eligible |        |           |           |         | `EligibilityValue`new\_<br/> |

## AuthorMapping

| Name               | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                |
| ------------------ | ------ | --------- | --------- | ------- | -------------------------------------------------------- |
| Add association    |        |           |           |         | `NimbusId`nimbus_id<br/>                                 |
| Update association |        |           |           |         | `NimbusId`old_nimbus_id<br/>`NimbusId`new_nimbus_id<br/> |
| Clear association  |        |           |           |         | `NimbusId`nimbus_id<br/>                                 |
| Remove keys        |        |           |           |         |                                                          |
| Set keys           |        |           |           |         | `Vecu8`keys<br/>                                         |

## DmpQueue

| Name               | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                            |
| ------------------ | ------ | --------- | --------- | ------- | ---------------------------------------------------- |
| Service overweight |        |           |           |         | `OverweightIndex`index<br/>`Weight`weight_limit<br/> |

## PolkadotXcm

| Name                             | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                                                                 |
| -------------------------------- | ------ | --------- | --------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Send                             |        |           |           |         | `BoxVersionedMultiLocation`dest<br/>`BoxVersionedXcmTuple`message<br/>                                                                                                    |
| Teleport assets                  |        |           |           |         | `BoxVersionedMultiLocation`dest<br/>`BoxVersionedMultiLocation`beneficiary<br/>`BoxVersionedMultiAssets`assets<br/>`u32`fee_asset_item<br/>                               |
| Reserve transfer assets          |        |           |           |         | `BoxVersionedMultiLocation`dest<br/>`BoxVersionedMultiLocation`beneficiary<br/>`BoxVersionedMultiAssets`assets<br/>`u32`fee_asset_item<br/>                               |
| Execute                          |        |           |           |         | `BoxVersionedXcmTasSysConfigCall`message<br/>`Weight`max_weight<br/>                                                                                                      |
| Force xcm version                |        |           |           |         | `BoxMultiLocation`location<br/>`XcmVersion`xcm_version<br/>                                                                                                               |
| Force default xcm version        |        |           |           |         | `OptionXcmVersion`maybe_xcm_version<br/>                                                                                                                                  |
| Force subscribe version notify   |        |           |           |         | `BoxVersionedMultiLocation`location<br/>                                                                                                                                  |
| Force unsubscribe version notify |        |           |           |         | `BoxVersionedMultiLocation`location<br/>                                                                                                                                  |
| Limited reserve transfer assets  |        |           |           |         | `BoxVersionedMultiLocation`dest<br/>`BoxVersionedMultiLocation`beneficiary<br/>`BoxVersionedMultiAssets`assets<br/>`u32`fee_asset_item<br/>`WeightLimit`weight_limit<br/> |
| Limited teleport assets          |        |           |           |         | `BoxVersionedMultiLocation`dest<br/>`BoxVersionedMultiLocation`beneficiary<br/>`BoxVersionedMultiAssets`assets<br/>`u32`fee_asset_item<br/>`WeightLimit`weight_limit<br/> |

## XcmpQueue

| Name                              | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                            |
| --------------------------------- | ------ | --------- | --------- | ------- | ---------------------------------------------------- |
| Service overweight                |        |           |           |         | `OverweightIndex`index<br/>`Weight`weight_limit<br/> |
| Suspend xcm execution             |        |           |           |         |                                                      |
| Resume xcm execution              |        |           |           |         |                                                      |
| Update suspend threshold          |        |           |           |         | `u32`new\_<br/>                                      |
| Update drop threshold             |        |           |           |         | `u32`new\_<br/>                                      |
| Update resume threshold           |        |           |           |         | `u32`new\_<br/>                                      |
| Update threshold weight           |        |           |           |         | `Weight`new\_<br/>                                   |
| Update weight restrict decay      |        |           |           |         | `Weight`new\_<br/>                                   |
| Update xcmp max individual weight |        |           |           |         | `Weight`new\_<br/>                                   |

## AssetRegistry

| Name           | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                                                                                                                 |
| -------------- | ------ | --------- | --------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Register asset |        |           |           |         | `AssetMetadataBalanceCustomMetadata`metadata<br/>`OptionAssetId`asset_id<br/>                                                                                                                                             |
| Update asset   |        |           |           |         | `AssetId`asset_id<br/>`Optionu32`decimals<br/>`OptionVecu8`name<br/>`OptionVecu8`symbol<br/>`OptionBalance`existential_deposit<br/>`OptionOptionVersionedMultiLocation`location<br/>`OptionCustomMetadata`additional<br/> |

## XTokens

| Name                         | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                      |
| ---------------------------- | ------ | --------- | --------- | ------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Transfer                     |        |           |           |         | `CurrencyId`currency_id<br/>`Balance`amount<br/>`BoxVersionedMultiLocation`dest<br/>`Weight`dest_weight<br/>                   |
| Transfer multiasset          |        |           |           |         | `BoxVersionedMultiAsset`asset<br/>`BoxVersionedMultiLocation`dest<br/>`Weight`dest_weight<br/>                                 |
| Transfer with fee            |        |           |           |         | `CurrencyId`currency_id<br/>`Balance`amount<br/>`Balance`fee<br/>`BoxVersionedMultiLocation`dest<br/>`Weight`dest_weight<br/>  |
| Transfer multiasset with fee |        |           |           |         | `BoxVersionedMultiAsset`asset<br/>`BoxVersionedMultiAsset`fee<br/>`BoxVersionedMultiLocation`dest<br/>`Weight`dest_weight<br/> |
| Transfer multicurrencies     |        |           |           |         | `VecTupleCurrencyIdBalance`currencies<br/>`u32`fee_item<br/>`BoxVersionedMultiLocation`dest<br/>`Weight`dest_weight<br/>       |
| Transfer multiassets         |        |           |           |         | `BoxVersionedMultiAssets`assets<br/>`u32`fee_item<br/>`BoxVersionedMultiLocation`dest<br/>`Weight`dest_weight<br/>             |

## Crowdloan

| Name                               | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                            |
| ---------------------------------- | ------ | --------- | --------- | ------- | -------------------------------------------------------------------------------------------------------------------- |
| Associate native identity          |        |           |           |         | `AccountId`reward_account<br/>`RelayChainAccountId`relay_account<br/>`MultiSignature`proof<br/>                      |
| Change association with relay keys |        |           |           |         | `AccountId`reward_account<br/>`AccountId`previous_account<br/>`VecTupleRelayChainAccountIdMultiSignature`proofs<br/> |
| Claim                              |        |           |           |         |                                                                                                                      |
| Update reward address              |        |           |           |         | `AccountId`new_reward_account<br/>                                                                                   |
| Complete initialization            |        |           |           |         | `VestingBlockNumber`lease_ending_block<br/>                                                                          |
| Initialize reward vec              |        |           |           |         | `VecTupleRelayChainAccountIdOptionAccountIdBalanceOfT`rewards<br/>                                                   |
