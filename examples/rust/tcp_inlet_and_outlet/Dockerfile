FROM ghcr.io/ockam-network/ockam/builder@sha256:217f5dd606c71dca97bce17d2472a48b9874ff7c4bebaace7764e51377ff7eca as builder
COPY . .
RUN set -xe; cd examples/rust/tcp_inlet_and_outlet; cargo build --release --examples

FROM ghcr.io/ockam-network/ockam/base@sha256:ea156477d425e92640ec8574663f598bc019269a12ed0fefb5ad48256afff4e0
COPY --from=builder /work/target/release/examples/* /usr/bin/
