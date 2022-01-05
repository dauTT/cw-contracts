# install cargo-generate
cargo install cargo-generate --features vendored-openssl
cargo generate --git https://github.com/CosmWasm/cosmwasm-template.git --name my-first-contract
cd my-first-contract
-------------------------------------------------------------------------------------------

cargo wasm

cargo install cargo-run-script


----------------------------------------

junod tx wasm instantiate 306   '{"count":2}'    --from  valink --fees=4000ujunox  --gas auto   --label "first cw - Chandrodaya"

junod  query  tx  6963A6275E73F6EB30441353AC3107B7D2377A044F3E0228FCF43DEF165BE4A0 --node="https://rpc.uni.junomint.com:443"


junod  query wasm  list-contract-by-code 306 --node="https://rpc.uni.junomint.com:443"
contracts:
- juno1yrzxr3s4elxql3e7l4vf2cywd4rcyntl27rc63mqxa7a3xwtkerqzrj0sz
pagination:
  next_key: null
  total: "0"

-----------------------------------------------------------------------------------

junod  query wasm  contract  juno1yrzxr3s4elxql3e7l4vf2cywd4rcyntl27rc63mqxa7a3xwtkerqzrj0sz
address: juno1yrzxr3s4elxql3e7l4vf2cywd4rcyntl27rc63mqxa7a3xwtkerqzrj0sz
contract_info:
  admin: ""
  code_id: "306"
  created: null
  creator: juno1scnjt6xmmej5l6acfr5nujhc6tea6w0kmrvea5
  extension: null
  ibc_port_id: ""
  label: first cw - Chandrodaya

-----------------------------------------------
junod  query wasm contract-state all  juno1yrzxr3s4elxql3e7l4vf2cywd4rcyntl27rc63mqxa7a3xwtkerqzrj0sz

models:
- key: 636F6E74726163745F696E666F
  value: eyJjb250cmFjdCI6ImNyYXRlcy5pbzpteS1maXJzdC1jb250cmFjdCIsInZlcnNpb24iOiIwLjEuMCJ9
- key: "7374617465"
  value: eyJjb3VudCI6Miwib3duZXIiOiJqdW5vMXNjbmp0NnhtbWVqNWw2YWNmcjVudWpoYzZ0ZWE2dzBrbXJ2ZWE1In0=
pagination:
  next_key: null
  total: "0"

-----------------------------------------------
junod  query wasm contract-state smart  juno1yrzxr3s4elxql3e7l4vf2cywd4rcyntl27rc63mqxa7a3xwtkerqzrj0sz  '{"get_count":{}}'

data:
  count: 2


-----------------------------------------------
junod  tx wasm execute  juno1yrzxr3s4elxql3e7l4vf2cywd4rcyntl27rc63mqxa7a3xwtkerqzrj0sz  '{"increment":{}}' --from valink --gas auto --fees 3500ujunox

junod  query wasm contract-state smart  juno1yrzxr3s4elxql3e7l4vf2cywd4rcyntl27rc63mqxa7a3xwtkerqzrj0sz  '{"get_count":{}}'
data:
  count: 3

-----------------------------------------------

junod  tx wasm execute  juno1yrzxr3s4elxql3e7l4vf2cywd4rcyntl27rc63mqxa7a3xwtkerqzrj0sz  '{"reset":{"count":100}}' --from valink --gas auto --fees 3500ujunox

junod  query wasm contract-state smart  juno1yrzxr3s4elxql3e7l4vf2cywd4rcyntl27rc63mqxa7a3xwtkerqzrj0sz  '{"get_count":{}}'
data:
  count: 100
----------------------------------------------

https://blueprints.juno.giansalex.dev/#/contracts/juno1yrzxr3s4elxql3e7l4vf2cywd4rcyntl27rc63mqxa7a3xwtkerqzrj0sz
