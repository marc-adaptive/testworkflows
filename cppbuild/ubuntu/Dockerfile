FROM ubuntu as builder

RUN echo 'HI' > test.txt

FROM scratch as essential-artifacts

COPY --from=builder ./*.txt /