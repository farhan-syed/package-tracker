<script context="module">
  export function returnUrl(carrier, tracking) {
    switch (carrier) {
      case 'USPS':
        return `https://tools.usps.com/go/TrackConfirmAction?tLabels=${tracking}`
      case 'UPS':
        return `https://wwwapps.ups.com/WebTracking/track?track=yes&trackNums=${tracking}`
      case 'FedEx':
        return `https://www.fedex.com/apps/fedextrack/?tracknumbers=${tracking}`
      case 'DHL':
        return `https://www.dhl.com/en/express/tracking.html?tracking-id=${tracking}`
      case 'OnTrac':
        return `https://www.ontrac.com/trackingdetail.asp?tracking=${tracking}`
      case 'Canada Post':
        return `https://www.canadapost.ca/cpotools/apps/track/personal/findByTrackNumber?trackingNumber=${tracking}`
      case 'Royal Mail':
        return `https://www.royalmail.com/track-your-item/?trackNumber=${tracking}`
    }
  }
</script>
