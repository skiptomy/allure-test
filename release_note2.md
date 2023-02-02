# Changelog: 
## Feature
### Catalog
PR: [ add no_fs report status for data_items ](https://github.com/elastio/blue-stack/pull/5958)
- As we discussed on daily, there is a case when fs-check does not contain partitions, it supposed to mean that there is empty no_fs volume. So here:
1) When show data_item_snapshots we now for such volumes return no_fs status
2) We now do not show in list or filter values reports that have no partitions at all, or separate volumes with no partitions.

- Ticket(s): Not specified
- Author(s): rkaiafiuk@elastio.com
- Commit hash: [5e19d8bfeb19cbe15fe113bf7c9b3091c3b0ad9c](https://github.com/elastio/blue-stack/commit/5e19d8bfeb19cbe15fe113bf7c9b3091c3b0ad9c)
- QA tips:
  - Not specified
***
### E2e
PR: [ #5301 - add cc installation using ui to e2e tests ](https://github.com/elastio/blue-stack/pull/5925)
- Added scenario with Cloud Connector installation using UI to e2e tests
## Task link
Closes #5301

- Ticket(s): Not specified
- Author(s): skiptomy55@gmail.com
- Commit hash: [d60bc9f583615d403f9a5643a230b542432752e6](https://github.com/elastio/blue-stack/commit/d60bc9f583615d403f9a5643a230b542432752e6)
- QA tips:
  - Not specified
***
### Infra
PR: [ promtail: add cri parsing pipeline ](https://github.com/elastio/blue-stack/pull/5954)
- It looks like with 1.24 k8s new logging format has been introduced, k8s-logs, thus promtail parsing had to be adjusted to ease Grafana logs manipulation on users' side.
## Task link
Close https://github.com/elastio/blue-stack/issues/5951.

- Ticket(s): Not specified
- Author(s): 75213+ivankovnatsky@users.noreply.github.com
- Commit hash: [a53ef365728a84fff23247a81f2cb684c8143630](https://github.com/elastio/blue-stack/commit/a53ef365728a84fff23247a81f2cb684c8143630)
- QA tips:
  - Not specified
***
### Reports
PR: [ #5590 - rename reports columns for csv export ](https://github.com/elastio/blue-stack/pull/5962)
- - Report templates cells were remained in accordance with data fields names for csv export; 
- Empty Backup Date value is set to empty string
## Task link
Part of #5590

- Ticket(s): Not specified
- Author(s): lagutochkina@gmail.com
- Commit hash: [6cf55ef4b37a2e54dec4412350da2b1744bc0f9a](https://github.com/elastio/blue-stack/commit/6cf55ef4b37a2e54dec4412350da2b1744bc0f9a)
- QA tips:
  - Not specified
***
PR: [ #5590 - update dashboard and reports templates ](https://github.com/elastio/blue-stack/pull/5947)
- Dashboard and reports templates were updated:
- "Account Alias" column was added
- Columns names were updated
- Statuses names were mapped to the new names
- Countable field "TimeToCompleteBackup" was added with appropriate formula
- "BackupDaysOld" is now a countable from "MinutesSince" (days from minutes formula)
- All "N/A" values were replaced with required values (empty string or 0)
## Task link
Part of #5590

- Ticket(s): Not specified
- Author(s): lagutochkina@gmail.com
- Commit hash: [8f2b88212cd6314a4d7bc40ebad66e94f39f8fcb](https://github.com/elastio/blue-stack/commit/8f2b88212cd6314a4d7bc40ebad66e94f39f8fcb)
- QA tips:
  - Not specified
***
### Ui
PR: [ #5936 - update radio tabs labels on policy pages ](https://github.com/elastio/blue-stack/pull/5943)
- - Radio tabs labels were updated on Add, Edit and Default policy pages
- Tooltips were added for "Protect all EBS volumes" and "Protect all EC2 and EBS" radio tabs
- Also on the FS check reports list page, the default selection was changed to "This Month"
## Task link
Closes #5936

- Ticket(s): Not specified
- Author(s): lagutochkina@gmail.com
- Commit hash: [b7ec07f3f360d03c981d3e385f66a4e77ddfe67d](https://github.com/elastio/blue-stack/commit/b7ec07f3f360d03c981d3e385f66a4e77ddfe67d)
- QA tips:
  - Not specified
***
## Fix
### Catalog
PR: [ #6763 - do not mix-up debug info files ](https://github.com/elastio/blue-stack/pull/5937)
- This PR prevents mix-up of ransomware debug info files during processing of iScan reports.
**Other improvements:**
- Prevent accidental attachment overrides on retries after request token expiration.
- Do not hold full reports in memory while processing them.
## Task link
Closes elastio/elastio#6763

- Ticket(s): Not specified
- Author(s): 47307091+isum@users.noreply.github.com
- Commit hash: [0da4d4ee7dea90c89ddaf8e73d2cf2c64d55d43f](https://github.com/elastio/blue-stack/commit/0da4d4ee7dea90c89ddaf8e73d2cf2c64d55d43f)
- QA tips:
  - Not specified
***
### Infra
PR: [ vmagent: add pdb and increase replica count ](https://github.com/elastio/blue-stack/pull/5924)
- We need to make sure that we service at least half of the victoria
metrics workload during disruptions and deployments.

- Ticket(s): Not specified
- Author(s): 75213+ivankovnatsky@users.noreply.github.com
- Commit hash: [d990cacf98544263d2aed0333fb119ba8be0b4ee](https://github.com/elastio/blue-stack/commit/d990cacf98544263d2aed0333fb119ba8be0b4ee)
- QA tips:
  - Not specified
***
### Pechkin
PR: [ fix elastio:backup-policy:compliance-check:succeeded having wrong end time label ](https://github.com/elastio/blue-stack/pull/5964)
- There was a type in label value causing the same timestamp to be used for both start and end.
## Task link
Hotfix

- Ticket(s): Not specified
- Author(s): abarkovsky@elastio.com, anton@swarmer.me
- Commit hash: [b14bcc08615b8ac4975bdc5edd2dc54c926416bb](https://github.com/elastio/blue-stack/commit/b14bcc08615b8ac4975bdc5edd2dc54c926416bb)
- QA tips:
  - Not specified
***
### Ui
PR: [ retry request max time incrisead ](https://github.com/elastio/blue-stack/pull/5960)
-  increased max request time from 5sec -> 60sec

- Ticket(s): Not specified
- Author(s): nikolas.ryabchenko@gmail.com
- Commit hash: [fefc4a31c77f2c7a7d51743e55a7bc64da11be5e](https://github.com/elastio/blue-stack/commit/fefc4a31c77f2c7a7d51743e55a7bc64da11be5e)
- QA tips:
  - Not specified
***
PR: [ #5461 - complience report page header fixes ](https://github.com/elastio/blue-stack/pull/5952)
- - Header text changed
- Fixed bug when re-entering page again

- Ticket(s): Not specified
- Author(s): nikolas.ryabchenko@gmail.com
- Commit hash: [d5d6ca4f4544becf3e68ef2f67e6ddfbdaa8ee4d](https://github.com/elastio/blue-stack/commit/d5d6ca4f4544becf3e68ef2f67e6ddfbdaa8ee4d)
- QA tips:
  - Not specified
***
PR: [ fs check status icon ](https://github.com/elastio/blue-stack/pull/5942)
- Popover for recovery point status was fixed
## Task link
Closes #5797 

- Ticket(s): Not specified
- Author(s): 63728704+OlhaTitova@users.noreply.github.com, o.titova.ua@gmail.com
- Commit hash: [dbbdc9de5390f81b35552a30910435257d73c02b](https://github.com/elastio/blue-stack/commit/dbbdc9de5390f81b35552a30910435257d73c02b)
- QA tips:
  - Not specified
***
## Chore
### Rs
PR: [ update red-stack crate to 0.23.44 ](https://github.com/elastio/blue-stack/pull/5968)
- Updates crate `red-stack` to 0.23.44
## Task link
no

- Ticket(s): Not specified
- Author(s): svernidub@gmail.com
- Commit hash: [3b1087891285163bfe4f516dfd1b53e5036f8ae4](https://github.com/elastio/blue-stack/commit/3b1087891285163bfe4f516dfd1b53e5036f8ae4)
- QA tips:
  - Not specified
***
## Revert
### Infra
PR: [ enable istio in monitoring namespace ](https://github.com/elastio/blue-stack/pull/5955)
- We needed it to be disabled to make Victoria Metrics migration work.

- Ticket(s): Not specified
- Author(s): 75213+ivankovnatsky@users.noreply.github.com
- Commit hash: [30d3b511b79b3f68bebf3a64774a85fe2ed17d57](https://github.com/elastio/blue-stack/commit/30d3b511b79b3f68bebf3a64774a85fe2ed17d57)
- QA tips:
  - Not specified
***
 # Post-release tasks: 
## Pechkin
PR: [ fix elastio:backup-policy:compliance-check:succeeded having wrong end time label ](https://github.com/elastio/blue-stack/pull/5964)
- Not specified
- Author(s): abarkovsky@elastio.com, anton@swarmer.me
- Commit hash: [b14bcc08615b8ac4975bdc5edd2dc54c926416bb](https://github.com/elastio/blue-stack/commit/b14bcc08615b8ac4975bdc5edd2dc54c926416bb)
- Once the release has been fully deployed:
Delete all events of kind `elastio:backup-policy:compliance-check:succeeded`.
Then run the following command for the pechkin service:
```bash
./app --config configs/config.yaml regenerate-backup-window-succeeded-events
```
This command will regenerate all `elastio:backup-policy:compliance-check:succeeded` events and throw them into the `notifications` service.
***